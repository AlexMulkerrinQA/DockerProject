FROM ubuntu
MAINTAINER blubber:alex

RUN sudo apt-get  install git -y
RUN sudo apt-get  install apache2 -y
RUN git clone https://github.com/AlexMulkerrin/LudumDare35.git
RUN sudo cp -R LudumDare35/ /var/www/html/pretties
CMD echo "Setup webserver with Javascript project. Goto <ip>/pretties to see!"
