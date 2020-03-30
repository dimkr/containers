FROM alpine:edge

RUN apk add gcc musl-dev linux-headers samurai python3 py3-pip xz git ccache git-lfs byacc flex bash && pip install meson awscli && git-lfs install && for v in 0.46.1 0.51.2; do python3 -m venv /opt/meson-$v && . /opt/meson-$v/bin/activate && pip3 install meson==$v && printf "#!/bin/sh -e\n. /opt/meson-$v/bin/activate\nexec meson \"\$@\"" > /usr/local/bin/meson-$v && chmod 755 /usr/local/bin/meson-$v; done
