FROM golang as builder
RUN mkdir /app
ADD https://raw.githubusercontent.com/adterskov/geekbrains-conteinerization/master/homework/2.docker/golang/go.mod /app
ADD https://raw.githubusercontent.com/adterskov/geekbrains-conteinerization/master/homework/2.docker/golang/go.sum /app
ADD https://raw.githubusercontent.com/adterskov/geekbrains-conteinerization/master/homework/2.docker/golang/main.go /app
ADD . /app/ 
WORKDIR /app 
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -installsuffix cgo -o main .
FROM scratch
COPY --from=builder /app/main /
EXPOSE 8080
CMD ["/app/main"]
