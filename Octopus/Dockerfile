FROM alpine:latest
RUN apk add --no-cache ca-certificates
WORKDIR /app
COPY --from=ghcr.io/bestruirui/octopus:latest-alpine /app/octopus /app/octopus

RUN adduser \
    --disabled-password \
    --gecos "" \
    --home "/nonexistent" \
    --shell "/sbin/nologin" \
    --no-create-home \
    --uid 10014 \
    "choreo"
RUN chown -R "10014:10014" /app && chmod +x /app/octopus
# Use the above created unprivileged user
USER 10014


# Set the entrypoint to the executable
ENTRYPOINT ["/app/octopus"]
CMD ["start"]