FROM       ubuntu:22.04
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND         "noninteractive"
ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "openssl"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN apt-get update                               && \
    apt-get -y dist-upgrade                      && \
    apt-get --no-install-recommends                 \
            -y install aptitude                     \
                       ca-certificates              \
                       cron                         \
                       curl                         \
                       git                          \
                       gnupg2                       \
                       locales                      \
                       locales-all                  \
                       openssh-client               \
                       openssl                      \
                       python3                      \
                       python3-apt                  \
                       python3-dev                  \
                       python3-pip                  \
                       python3-setuptools           \
                       rsync                        \
                       sudo                      && \
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
                 --user "ansible-core == 2.13.*" && \
    rm -rf /root/.cache                             \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
