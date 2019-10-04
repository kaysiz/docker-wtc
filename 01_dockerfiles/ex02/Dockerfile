FROM ruby
LABEL Description="Containerizes a Ruby on Rails application."
LABEL maintainer="ksiziva <ksiziva@student.wethinkcode.co.za>"
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "sqlite3"]
RUN ["apt-get", "install", "-y", "nodejs"]
RUN ["gem", "install", "rails"]
ONBUILD COPY [".", "/opt/app"]
ONBUILD WORKDIR /opt/app
ONBUILD RUN ["bundle", "install"]
ONBUILD RUN ["rails", "db:migrate"]
ONBUILD RUN ["rails", "db:seed"]
ONBUILD EXPOSE 3000