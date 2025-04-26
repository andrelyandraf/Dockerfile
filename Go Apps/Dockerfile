FROM golang:1.14.6-buster AS Builder
WORKDIR /app
COPY . .
RUN GOO5=linux GOARCH=amd64 go build -o time-tz

FROM scratch
COPY --from=builder /app/time-tz /opt/time-tz
CMD ["/opt/time-tz"]
