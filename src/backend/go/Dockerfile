FROM golang:1.21.4-alpine3.18 AS builder
WORKDIR /app
COPY go.mod main.go .
RUN go build -o palette

FROM scratch
COPY --from=builder /app/palette .

EXPOSE 80

ENTRYPOINT ["/palette"]
