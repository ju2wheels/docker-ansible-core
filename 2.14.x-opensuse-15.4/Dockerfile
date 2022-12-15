FROM       opensuse/leap:15.4
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "openssl"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN zypper --non-interactive update                           && \
    zypper --non-interactive                                     \
           install --no-recommends                               \
                   cron                                          \
                   curl                                          \
                   git                                           \
                   gpg2                                          \
                   openssl                                       \
                   python310                                     \
                   python310-devel                               \
                   python310-pip                                 \
                   python310-setuptools                          \
                   rsync                                         \
                   sudo                                       && \
    python3.10 -m pip install --force-reinstall                  \
                              --upgrade                          \
                              --user pip                      && \
    python3.10 -m pip install --force-reinstall                  \
                              --upgrade                          \
                              --user setuptools               && \
    python3.10 -m pip install --force-reinstall                  \
                              --upgrade                          \
                              --user wheel                    && \
    python3.10 -m pip install --force-reinstall                  \
                              --upgrade                          \
                              --user "ansible-core == 2.14.*" && \
    rm -rf /root/.cache                                          \
           /var/cache/zypp

CMD        []
ENTRYPOINT ["ansible-playbook"]
