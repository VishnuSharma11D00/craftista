FROM golang:1.22.5-alpine3.20 as build

WORKDIR /build

COPY . .

RUN go build -o app


FROM alpine:3.20
WORKDIR /run

COPY --from=build /build/app .
COPY --from=build /build/templates .
COPY --from=build /build/static .
COPY --from=build /build/data .
COPY --from=build /build/api .

EXPOSE 8080

CMD ["./app"]
