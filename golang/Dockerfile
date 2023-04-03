FROM golang:latest

WORKDIR /opt/application

COPY go.mod go.sum /opt/application/

RUN go mod download

COPY .  /opt/application/

RUN go build -o build/fizzbuzz

EXPOSE 8080

CMD ["./build/fizzbuzz", "serve"]

