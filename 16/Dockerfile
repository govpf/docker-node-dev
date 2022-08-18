FROM govpf/node:16

RUN apt-get update && \
    DEBIAN_FRONTEND="noninteractive" \
    apt-get install -y --no-install-recommends \
      chromium \
      gconf-service \
      libasound2 \
      libatk1.0-0 \
      libatk1.0-0 \
      libdbus-1-3 \
      libgconf-2-4 \
      libgtk-3-0 \
      libnspr4 \
      libnss3 \
      libx11-xcb1 \
      libxss1 \
      libxtst6 \
      fonts-liberation \
      xdg-utils \
      lsb-release \
    && curl -L https://github.com/Yelp/dumb-init/releases/download/v1.2.1/dumb-init_1.2.1_amd64.deb > /tmp/dumb-init.deb \
    && dpkg -i /tmp/dumb-init.deb \
    && rm /tmp/dumb-init.deb \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["dumb-init"]

ENV CHROME_BIN /usr/bin/chromium
