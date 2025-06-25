FROM golang:1.21-alpine

WORKDIR /app

COPY . .

RUN go mod init service1    # Optional inside Docker, but better to do locally
RUN go build -o main .

EXPOSE 8001

CMD ["./main"]
