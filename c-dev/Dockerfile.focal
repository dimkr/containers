FROM ubuntu:focal

ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV ENV DEBIAN_FRONTEND noninteractive

RUN dpkg --add-architecture i386 && sed -i s/^deb.*multiverse.*/\#\&/g /etc/apt/sources.list && apt-get -qq update && apt-get -y upgrade && apt-get -y --no-install-recommends install gcc ninja-build locales python3-pip python3-setuptools python3-wheel python3-requests valgrind libc6:i386 libstdc++6:i386 zlib1g:i386 libmpc3:i386 xz-utils git make qemu-user-static ccache libncurses5-dev python3-venv strace git-lfs byacc flex wget gnupg autoconf automake libtool afl++ gdb-multiarch zstd doxygen graphviz && git-lfs install
RUN wget -q http://mirrors.kernel.org/ubuntu/pool/main/m/mpfr4/libmpfr4_3.1.4-1_amd64.deb && dpkg -i libmpfr4_3.1.4-1_amd64.deb && rm -f libmpfr4_3.1.4-1_amd64.deb && wget -q http://mirrors.kernel.org/ubuntu/pool/main/m/mpfr4/libmpfr4_3.1.4-1_i386.deb && dpkg -i libmpfr4_3.1.4-1_i386.deb && rm -f libmpfr4_3.1.4-1_i386.deb
RUN locale-gen --lang en_US.UTF-8 && python3 -m pip install --no-use-pep517 meson && python3 -m pip install awscli gcovr git-filter-repo && for v in 0.46.1 0.51.2; do python3 -m venv /opt/meson-$v && . /opt/meson-$v/bin/activate && python3 -m pip install wheel && python3 -m pip install meson==$v && printf "#!/bin/sh -e\n. /opt/meson-$v/bin/activate\nexec meson \"\$@\"" > /usr/local/bin/meson-$v && chmod 755 /usr/local/bin/meson-$v; done
RUN for i in arm-any32-linux-musleabi armeb-any32-linux-musleabi mips-any32-linux-musl mipsel-any32-linux-musl i386-any32-linux-musl; do wget -qO- https://github.com/dimkr/toolchains/releases/latest/download/$i.tar.gz | tar -xzf - -C /; done
