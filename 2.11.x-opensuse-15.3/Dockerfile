FROM       opensuse/leap:15.3
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "openssl"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN zypper --non-interactive update              && \
    zypper --non-interactive                        \
           install --no-recommends                  \
                   cron                             \
                   curl                             \
                   git                              \
                   gpg2                             \
                   openssl                          \
                   python3                          \
                   python3-devel                    \
                   python3-pip                      \
                   python3-setuptools               \
                   rsync                            \
                   sudo                          && \
    python3 -m pip install --force-reinstall        \
                           --upgrade                \
                           --user pip            && \
    python3 -m pip install --force-reinstall        \
                           --upgrade                \
                           --user setuptools     && \
    python3 -m pip install --force-reinstall        \
                           --upgrade                \
                           --user wheel          && \
    python3 -m pip install --force-reinstall        \
                 --upgrade                          \
                 --user "ansible-base == 2.11.*" && \
    rm -rf /root/.cache                             \
           /var/cache/zypp

CMD        []
ENTRYPOINT ["ansible-playbook"]
