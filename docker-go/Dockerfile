FROM golang:1.16.4-alpine3.13 AS build

WORKDIR /go/app

ADD . .

RUN go mod init full-cycle
RUN CGO_ENABLED=0 go build -o app


FROM scratch AS production

COPY --from=build /go/app/app /app

ENTRYPOINT ["/app"]