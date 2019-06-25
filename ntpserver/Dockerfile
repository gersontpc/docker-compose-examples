FROM alpine:latest
RUN apk add --no-cache openntpd

COPY ntp.conf /etc/
EXPOSE 123/udp
HEALTHCHECK CMD ntpctl -s status || exit 1

ENTRYPOINT [ "/usr/sbin/ntpd", "-v", "-d", "-s" ]