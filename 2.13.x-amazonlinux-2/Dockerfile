FROM       amazonlinux:2
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV LANG                    "en_US.UTF-8"
ENV LANGUAGE                "en_US.UTF-8"
ENV LC_ALL                  "en_US.UTF-8"
ENV PATH                    "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY      "nss"
ENV PYTHONDONTWRITEBYTECODE "1"
ENV PYTHONUNBUFFERED        "1"

RUN yum upgrade -y                               && \
    amazon-linux-extras install -y python3.8     && \
    yum install -y crontabs                         \
                   curl                             \
                   git                              \
                   gnupg2                           \
                   openssl                          \
                   python38                         \
                   python38-devel                   \
                   python38-pip                     \
                   python38-setuptools              \
                   rsync                            \
                   sudo                          && \
    python3.8 -m pip install --force-reinstall      \
                           --upgrade                \
                           --user pip            && \
    python3.8 -m pip install --force-reinstall      \
                           --upgrade                \
                           --user setuptools     && \
    python3.8 -m pip install --force-reinstall      \
                           --upgrade                \
                           --user wheel          && \
    python3.8 -m pip install --force-reinstall      \
                 --upgrade                          \
                 --user "ansible-core == 2.13.*" && \
    rm -rf /root/.cache                             \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
