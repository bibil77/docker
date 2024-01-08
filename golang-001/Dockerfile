FROM golang:1.16-alpine AS build

WORKDIR /app

COPY . .

RUN apk --no-cache add git && \
    CGO_ENABLED=0 GOOS=linux go build -o goland -a -installsuffix cgo .

FROM scratch

WORKDIR /app

COPY --from=build /app/goland .

CMD ["./goland"]