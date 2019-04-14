FROM alpine:latest AS builder
WORKDIR /tmp
RUN apk --no-cache add curl gcc libc-dev make
RUN curl -O http://www.udpxy.com/download/udpxy/udpxy-src.tar.gz && \
    tar -xzvf udpxy-src.tar.gz && \
    cd udpxy-1.0.23-12 && make && make install

FROM alpine:latest
RUN apk --no-cache add ca-certificates
COPY --from=builder /usr/local/bin/udpxy /usr/local/bin/udpxrec /usr/local/bin/

USER nobody
CMD ["/usr/local/bin/udpxy", "-T", "-p", "4022"]
