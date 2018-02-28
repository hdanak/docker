FROM jetbrains/teamcity-agent

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y sendemail
RUN apt-get install -y s3cmd

RUN curl -L https://www.opscode.com/chef/install.sh | bash -s -- -P chefdk
