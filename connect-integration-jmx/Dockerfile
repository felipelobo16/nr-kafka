FROM maven:3-jdk-11 as builder-mvn
RUN git clone https://github.com/newrelic/nrjmx && \
    cd nrjmx && \
    mvn package -DskipTests -P \!deb,\!rpm,\!test,\!tarball

FROM golang:1.18 as go
ENV CGO_ENABLED=0
ENV GOOS=linux
WORKDIR /go/src/nri-jmx/
RUN git clone --depth 1 -b v3.2.1 https://github.com/newrelic/nri-jmx.git .
RUN make clean compile

FROM alpine:latest
RUN mkdir /binares
COPY --from=go /go/src/nri-jmx/bin/nri-jmx /binares
COPY --from=builder-mvn /nrjmx/bin/nrjmx /binares
COPY --from=builder-mvn /nrjmx/bin/nrjmx.jar /binares

ENTRYPOINT ["tail", "-f", "/dev/null"]
