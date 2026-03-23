FROM alpine:latest
RUN apk add --no-cache tzdata
WORKDIR /app
COPY --from=eceasy/cli-proxy-api:latest /app/CLIProxyAPI ./CLIProxyAPI
COPY config.example.yaml /CLIProxyAPI/config.example.yaml

RUN adduser \
    --disabled-password \
    --gecos "" \
    --home "/nonexistent" \
    --shell "/sbin/nologin" \
    --no-create-home \
    --uid 10014 \
    "choreo"
# Use the above created unprivileged user
USER 10014

# Set the entrypoint to the executable
ENTRYPOINT ["./CLIProxyAPI"]