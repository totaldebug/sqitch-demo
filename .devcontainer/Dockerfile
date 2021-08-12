FROM python:latest

WORKDIR /workspace

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y zsh cpanminus perl perl-doc libdbd-pg-perl lsb-release build-essential
RUN cpanm --quiet --notest App::Sqitch

RUN sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
RUN apt-get update
RUN apt-get install -y postgresql-client

CMD ["zsh"]
