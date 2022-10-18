FROM       rockylinux:9
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "nss"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN dnf upgrade -y                               && \
    dnf install -y crontabs                         \
                   curl                             \
                   dnf                              \
                   git                              \
                   glibc-langpack-en                \
                   gnupg2                           \
                   openssl                          \
                   python3                          \
                   python3-devel                    \
                   python3-dnf                      \
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
                 --user "ansible-core == 2.11.*" && \
    rm -rf /root/.cache                             \
           /var/cache/dnf

CMD        []
ENTRYPOINT ["ansible-playbook"]
