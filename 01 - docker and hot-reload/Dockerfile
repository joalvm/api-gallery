# Etapa de construcción
FROM golang:1.21-alpine

WORKDIR /app

COPY . .

RUN apk add --no-cache git gcc musl-dev make

RUN go install github.com/githubnemo/CompileDaemon@latest

# Etapa de ejecución usando Makefile
ENTRYPOINT CompileDaemon --build="make clean && make build" --command="./bin/api" -build-dir=/app -color=true