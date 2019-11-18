#this creates a webaplication
#
# docker build -t vtenisheva/my_private:web_app .
# docker run -d -p 5000:5000 vtenisheva/my_private:web_app

FROM centos:7
MAINTAINER vtenisheva

USER root

# install some tools
RUN yum install -y curl sudo ip python3 epel-release python3-pip python3-virtualenv


# get directory with files 

COPY student-exam2/ /student-exam2

WORKDIR /student-exam2

# installation
RUN python3 -m venv venv
RUN . venv/bin/activate
RUN pip3 install -e .

#entrypoint

#export FLASK_APP=js_example
#export LC_ALL=en_US.utf8
#export LANG=en_US.utf8
#flask run -h 0.0.0.0 -p 5000

COPY entrypoint.sh /
ENTRYPOINT [ "sh", "/entrypoint.sh" ]

# ports
EXPOSE 5000

