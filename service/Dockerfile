######## Start a new stage from alpine #######

FROM alpine:3.12

LABEL maintainer="Sergey Denisov <DenisovS21@gmail.com>"

RUN apk update && \
    apk upgrade && \
    apk add ca-certificates && \
    update-ca-certificates && \
    apk add tzdata

RUN rm -rf /var/cache/apk/*

ENV TZ=Asia/Novosibirsk

WORKDIR /root/

RUN wget https://github.com/fc-testzone/binary-storage/raw/main/binary-service
RUN chmod +x binary-service
RUN mkdir /var/log/apiserver/

CMD ["./binary-service"]
