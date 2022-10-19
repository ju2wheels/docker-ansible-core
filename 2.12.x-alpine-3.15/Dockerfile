FROM       alpine:3.15
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "openssl"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN apk upgrade --latest --update-cache          && \
    apk add bash                                    \
            build-base                              \
            cmd:pip3                                \
            curl                                    \
            git                                     \
            gnupg                                   \
            openssh-client                          \
            openssl                                 \
            python3                                 \
            python3-dev                             \
            rsync                                   \
            shadow                                  \
            sudo                                 && \
    apk add --virtual ansible-build-deps            \
            cargo                                   \
            libffi-dev                              \
            openssl-dev                             \
            rust                                 && \
    python3 -m pip install --force-reinstall        \
                            --upgrade               \
                            --user pip           && \
    python3 -m pip install --force-reinstall        \
                            --upgrade               \
                            --user setuptools    && \
    python3 -m pip install --force-reinstall        \
                           --upgrade                \
                           --user wheel          && \
    python3 -m pip install --force-reinstall        \
                 --upgrade                          \
                 --user "ansible-core == 2.12.*" && \
    apk del ansible-build-deps                   && \
    rm -rf /root/.cache                             \
           /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
