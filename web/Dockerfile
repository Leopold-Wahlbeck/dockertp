FROM golang:1.20 AS builder

WORKDIR /app
COPY . .
RUN go build dispatcher.go

FROM ubuntu:latest
WORKDIR /app

COPY --from=builder /app/dispatcher .
COPY static ./static

EXPOSE 80
CMD ["./dispatcher"]
