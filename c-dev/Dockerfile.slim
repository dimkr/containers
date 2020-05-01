FROM debian:buster-slim

ENV LC_ALL C
ENV LANG C

RUN apt-get -qq update && apt-get -y upgrade && apt-get -y --no-install-recommends install gcc libc6-dev ninja-build python3-minimal python3-pip python3-setuptools python3-wheel python3-venv xz-utils git ccache git-lfs byacc flex valgrind strace zstd && pip3 install meson awscli && git-lfs install && for v in 0.46.1 0.51.2; do python3 -m venv /opt/meson-$v && . /opt/meson-$v/bin/activate && pip3 install wheel && pip3 install meson==$v && printf "#!/bin/sh -e\n. /opt/meson-$v/bin/activate\nexec meson \"\$@\"" > /usr/local/bin/meson-$v && chmod 755 /usr/local/bin/meson-$v; done && apt-get autoremove --purge -y python3-pip python3-setuptools python3-wheel python3-venv
