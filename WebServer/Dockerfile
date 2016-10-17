FROM ubuntu
MAINTAINER blubber:alex

RUN sudo apt-get -y install git apache2
RUN git clone https://github.com/AlexMulkerrin/LudumDare35.git
RUN sudo cp -R LudumDare35/ /var/www/html/pretties
CMD echo "Setup webserver with Javascript project. Goto <ip>/pretties to see!"
