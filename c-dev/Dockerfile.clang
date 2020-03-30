FROM dimkr/c-dev:slim

RUN apt-get -qq update && apt-get -y install wget gnupg2
RUN wget -qO- https://apt.llvm.org/llvm-snapshot.gpg.key | apt-key add - && printf "deb http://apt.llvm.org/buster/ llvm-toolchain-buster-9 main\ndeb http://apt.llvm.org/buster/ llvm-toolchain-buster-10 main\ndeb http://apt.llvm.org/buster/ llvm-toolchain-buster main" > /etc/apt/sources.list.d/llvm.list && apt-get -qq update && apt-get -y --no-install-recommends install clang-9 llvm-9-dev clang-10 llvm-10-dev clang-11 llvm-11-dev && ln -s /usr/bin/clang-9 /usr/local/bin/clang
