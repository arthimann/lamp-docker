FROM httpd:2.4-buster

# Update
RUN apt-get -y update --fix-missing && \
    apt-get upgrade -y && \
    apt-get --no-install-recommends install -y apt-utils && \
    rm -rf /var/lib/apt/lists/*

# Install useful tools and install important libaries
RUN apt-get -y update && \
    apt-get -y --no-install-recommends install nano wget dialog libsqlite3-dev libsqlite3-0 && \
    apt-get -y --no-install-recommends install default-mysql-client zlib1g-dev libzip-dev libicu-dev && \
    apt-get -y --no-install-recommends install --fix-missing apt-utils build-essential git curl libonig-dev && \
    apt-get -y --no-install-recommends install --fix-missing libcurl4 libcurl4-openssl-dev zip openssl && \
    rm -rf /var/lib/apt/lists/*

COPY $PWD/httpd.conf /usr/local/apache2/conf/httpd.conf
COPY $PWD/extra/httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf


EXPOSE 80
EXPOSE 443
