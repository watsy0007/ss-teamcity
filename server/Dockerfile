FROM ubuntu
RUN apt-get update
RUN apt-get dist-upgrade -y

RUN DEBIAN_FRONTEND=noninteractive apt-get -y dist-upgrade
RUN apt-get install -y software-properties-common python-software-properties && add-apt-repository -y ppa:webupd8team/java
RUN apt-get update && apt-get -y upgrade
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java8-installer && apt-get install -y oracle-java8-set-default

RUN apt-get install -y wget tar
RUN mkdir /app
RUN mkdir /app/teamcity
WORKDIR /app
RUN wget https://d1opms6zj7jotq.cloudfront.net/teamcity/TeamCity-9.1.5.tar.gz
RUN tar -xvf /app/TeamCity-9.1.5.tar.gz -C /app/
EXPOSE 8111
CMD ["/app/TeamCity/bin/teamcity-server.sh", "run"]
#CMD ["ls", "-al", "/app/TeamCity"]

