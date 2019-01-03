# Add timezone database to alpine based image

Let's say your Go service needs to load a [Location](https://golang.org/pkg/time/#LoadLocation)

```go
tz, err := time.LoadLocation("America/New_York")
```

then you can add the timezone database to the final image

```docker
FROM alpine:latest
RUN apk add --no-cache tzdata
# ...
```

Alternatively you can mount the host's database file.
