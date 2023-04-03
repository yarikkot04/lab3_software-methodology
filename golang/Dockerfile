FROM golang AS builder

WORKDIR /opt/application

COPY go.mod go.sum /opt/application/

RUN go mod download

COPY .  /opt/application/

RUN go build -o build/fizzbuzz

FROM gcr.io/distroless/base

COPY --from=builder /opt/application/build/fizzbuzz /

COPY --from=builder /opt/application/templates/index.html /templates/

EXPOSE 8080

CMD ["/fizzbuzz", "serve"]

