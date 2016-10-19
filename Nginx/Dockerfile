FROM debian:jessie
MAINTAINER blubber:alex

RUN apt-get update -y
RUN apt-get install git -y
RUN apt-get install nginx -y
RUN apt-get install mysql-client -y
EXPOSE 80 443

RUN git clone https://github.com/AlexMulkerrin/LudumDare35.git
RUN cp -R LudumDare35/ /var/www/html/pretties

CMD ["nginx", "-g", "daemon off;"]
