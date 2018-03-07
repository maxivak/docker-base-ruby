FROM phusion/passenger-customizable:0.9.28

RUN apt-get update
RUN apt-get -y install libcurl3 git curl  wget     g++ libreadline6-dev zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3   autoconf libgdbm-dev   libncurses5-dev   automake   libtool  bison   pkg-config   libffi-dev   liblzma-dev   zlib1g-dev   libgmp-dev libgmp3-dev


# Set correct environment variables.
ENV HOME /root




# ruby 2.4
RUN /pd_build/ruby-2.4.*.sh

# Use baseimage-docker's init process.
CMD ["/sbin/my_init"]



# disable services
RUN touch /etc/service/nginx/down
RUN touch /etc/service/sshd/down
RUN touch /etc/service/cron/down
RUN touch /etc/service/syslog-ng/down
RUN touch /etc/service/syslog-forwarder/down
RUN touch /etc/service/nginx-log-forwarder/down


# yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update
RUN apt-get -y install yarn



# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*