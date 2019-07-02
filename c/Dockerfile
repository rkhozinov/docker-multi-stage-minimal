FROM alpine:latest AS compile-image
RUN apk add gcc libc-dev 

WORKDIR /root
COPY hello.c .
RUN gcc --static -o helloworld hello.c

FROM busybox:latest AS runtime-image

COPY --from=compile-image /root/helloworld .
CMD ["/helloworld"]
