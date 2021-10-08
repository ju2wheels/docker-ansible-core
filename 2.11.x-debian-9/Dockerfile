FROM       debian:9
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND         "noninteractive"
ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "openssl"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN apt-get update                                                && \
    apt-get -y dist-upgrade                                       && \
    apt-get --no-install-recommends                                  \
            -y install aptitude                                      \
                       ca-certificates                               \
                       cron                                          \
                       curl                                          \
                       git                                           \
                       gnupg2                                        \
                       locales                                       \
                       locales-all                                   \
                       openssh-client                                \
                       openssl                                       \
                       python3                                       \
                       python3-apt                                   \
                       python3-dev                                   \
                       python3-pip                                   \
                       python3-setuptools                            \
                       rsync                                         \
                       sudo                                       && \
    apt-get --no-install-recommends                                  \
            -y install build-essential                               \
                       curl                                          \
                       libbz2-dev                                    \
                       libncurses5-dev                               \
                       libncursesw5-dev                              \
                       libreadline-dev                               \
                       libssl-dev                                    \
                       libsqlite3-dev                                \
                       llvm                                          \
                       tk-dev                                        \
                       wget                                          \
                       xz-utils                                      \
                       zlib1g-dev                                 && \
    cd /tmp                                                       && \
    wget https://www.python.org/ftp/python/3.6.4/Python-3.6.4.tgz && \
    tar xzf Python-3.6.4.tgz                                      && \
    cd Python-3.6.4                                               && \
    ./configure                                                   && \
    make -j8 build_all                                            && \
    make -j8 altinstall                                           && \
    cd /                                                          && \
    rm -rf /tmp/Python-3.6.4.tgz /tmp/Python-3.6.4                && \
    python3 -m pip install --force-reinstall                         \
                           --upgrade                                 \
                           --user  'pip==20.3.4'                  && \
    python3 -m pip install --force-reinstall                         \
                           --upgrade                                 \
                           --user setuptools                      && \
    python3 -m pip install --force-reinstall                         \
                           --upgrade                                 \
                           --user wheel                           && \
    python3.6 -m pip install --force-reinstall                       \
                           --upgrade                                 \
                           --user  pip                            && \
    python3.6 -m pip install --force-reinstall                       \
                           --upgrade                                 \
                           --user setuptools                      && \
    python3.6 -m pip install --force-reinstall                       \
                           --upgrade                                 \
                           --user wheel                           && \
    python3.6 -m pip install --force-reinstall                       \
                 --upgrade                                           \
                 --user "ansible-core == 2.11.*"                  && \
    rm -rf /root/.cache                                              \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
