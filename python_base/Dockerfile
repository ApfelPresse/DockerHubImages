FROM alpine:latest

ENV PYTHONUNBUFFERED=1
ENV PROXY_HOST=127.0.0.1

RUN apk add --no-cache python3
RUN if [ ! -e /usr/bin/python ]; then ln -sf python3 /usr/bin/python ; fi

RUN python3 -m ensurepip
RUN rm -r /usr/lib/python*/ensurepip
RUN pip3 install --no-cache --upgrade pip setuptools wheel
RUN if [ ! -e /usr/bin/pip ]; then ln -s pip3 /usr/bin/pip ; fi

RUN pip3 install --no-cache pymongo 
RUN pip3 install --no-cache requests
RUN pip3 install --no-cache schedule
RUN pip3 install --no-cache fake_headers
RUN pip3 install --no-cache tqdm
RUN pip3 install --no-cache graphitesend
RUN pip3 install --no-cache feedparser
RUN pip3 install --no-cache python-dateutil
RUN pip3 install --no-cache Flask-Graphite
RUN pip3 install --no-cache flasgger

WORKDIR /app

CMD [ "python3", "main.py" ]