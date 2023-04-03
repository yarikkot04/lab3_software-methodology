FROM golang AS builder

WORKDIR /opt/application

COPY go.mod go.sum /opt/application/

RUN go mod download

COPY .  /opt/application/

RUN CGO_ENABLED=0 go build -ldflags "-w -s -extldflags '-static'" -o build/fizzbuzz

FROM scratch

COPY --from=builder /opt/application/build/fizzbuzz /

COPY --from=builder /opt/application/templates/index.html /templates/

EXPOSE 8080

CMD ["/fizzbuzz", "serve"]

