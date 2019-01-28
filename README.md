# docker-php-mssql-cron
  
Docker images based on the [official Docker PHP images](https://hub.docker.com/_/php/) with 
the [Microsoft SQL Server Driver](https://github.com/Microsoft/msphpsql) and [`cron`](https://manpages.debian.org/stretch/cron/cron.8.en.html) already installed.

Instead of an interactive PHP CLI (`CMD ["php", "-a"]`), this image runs `cron` with `CMD ["cron", "-f"]`. To change the [`crontab` file](https://manpages.debian.org/stretch/cron/crontab.5.en.html), mount a volume to `/etc/cron.d/custom`.

This repository uses [Namoshek/docker-php-mssql](https://github.com/Namoshek/docker-php-mssql) as base.

# Usage

You can pull one of the images with `docker pull namoshek/php-mssql-cron:<tag>`.
To run a container with an image, you can also use `docker run namoshek/php-mssql-cron:<tag>` directly.

The format of the crontab file should look like this:
```
* * * * *   root    /usr/local/bin/php /var/www/test.php
```

# Available Versions

For the moment, the primary goal of this repository is to support the following configurations:

- PHP 7.3 + Microsoft ODBC Driver 17 + sqlsrv + pdo_sqlsrv + cron (CLI only)

**Note: As there is currently no stable release of the [`microsoft/msphpsql`](https://github.com/Microsoft/msphpsql/releases) available, this build is considered experimental!**

The exact versions can vary from build to build.
To see a list of all available tags, please have a look at the [Docker Hub image page](https://hub.docker.com/r/namoshek/php-mssql-cron).

# Configuration

To change the PHP configuration, have a look at [the official PHP Docker image repository](https://hub.docker.com/_/php/).

# Contributing

If you want to contribute the sources for other PHP versions, I'll appreciate it. Please send a pull request.

# License

The code is licensed under the [MIT license](LICENSE).
