FROM ubuntu:18.04
RUN apt update && apt-get update && apt-get install  mysql-server nginx unzip apt-transport-https aspnetcore-runtime-3.1 
RUN wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
RUN sudo dpkg -i packages-microsoft-prod.deb
RUN dotnet --list-runtimes && systemctl start nginx && systemctl status nginx && mkdir /var/www/nopCommerce440 && cd /var/www/nopCommerce440
ADD https://github.com/nopSolutions/nopCommerce/releases/download/release-4.40.2/nopCommerce_4.40.2_NoSource_linux_x64.zip .
RUN unzip nopCommerce_4.40.2_NoSource_linux_x64.zip && mkdir bin && mkdir logs && cd ..
RUN chgrp -R www-data nopCommerce440/ && chown -R www-data nopCommerce440/