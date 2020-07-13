FROM python:3-alpine
WORKDIR /usr/speedtest
RUN pip install --no-cache-dir speedtest-cli && \
    speedtest-cli --csv-header > speedtest-results.csv && \
    # server 1249 - Nos Comunicacoes, S.A. (Lisboa, Portugal)
    echo "*/15 * * * * speedtest-cli --server 1249 --csv >> /usr/speedtest/speedtest-results.csv" > /etc/crontabs/root
CMD ["crond", "-f", "-d", "8"]