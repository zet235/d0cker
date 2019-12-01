FROM  alpine

COPY start.sh /start.sh

RUN chmod a+x /start.sh && \
    echo "**** install Python ****" && \
    apk add --no-cache python3 git && \
    if [ ! -e /usr/bin/python ]; then ln -sf python3 /usr/bin/python ; fi && \
    echo "**** install pip ****" && \
    python3 -m ensurepip && \
    rm -r /usr/lib/python*/ensurepip && \
    pip3 install --no-cache --upgrade pip setuptools wheel && \
    if [ ! -e /usr/bin/pip ]; then ln -s pip3 /usr/bin/pip ; fi && \
    git clone https://github.com/SystemRage/py-kms.git ~/py-kms && \
    pip install tzlocal pysqlite3


ENTRYPOINT ["/start.sh"]
