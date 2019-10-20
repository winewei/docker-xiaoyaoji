FROM inutano/wget:latest AS downloader

RUN wget -q https://raw.githubusercontent.com/winewei/tools/master/xiaoyaoji-2.1.5.tar.gz --no-check-certificate
RUN tar xf xiaoyaoji-2.1.5.tar.gz
RUN mv xiaoyaoji-2.1.5 ROOT

#final build
FROM pristtlt/docker-tomcat:7.0.90

COPY --from=downloader /ROOT ROOT/

EXPOSE 8080
CMD ["catalina.sh", "run"]
