FROM namoshek/php-mssql:7.3-cli

RUN apt-get update \
    && apt-get install -y cron

RUN echo "# Replace with your cron definitions" > /etc/cron.d/custom \
    && crontab /etc/cron.d/custom

CMD ["cron", "-f"]
