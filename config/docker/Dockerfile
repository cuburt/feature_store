FROM ubuntu:latest
RUN apt-get update && apt-get upgrade && apt-get install -y wget \
make software-properties-common gcc python3 python3-distutils python3-pip python3-apt \
redis-server
RUN mkdir app
WORKDIR /app
COPY ./ /app
RUN pip install feast[gcp] feast[redis]
ENV FEAST_USAGE=False
EXPOSE 6566
ENTRYPOINT ["feast"]
CMD ["--help"]