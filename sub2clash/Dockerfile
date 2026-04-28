FROM alpine:latest
WORKDIR /app
RUN chmod 777 /app
COPY --from=ghcr.io/bestnite/sub2clash:latest /app/sub2clash /app/sub2clash

RUN adduser \
    --disabled-password \
    --gecos "" \
    --home "/nonexistent" \
    --shell "/sbin/nologin" \
    --no-create-home \
    --uid 10014 \
    "choreo"
RUN chown -R "10014:10014" /app && chmod +x /app/sub2clash
# Use the above created unprivileged user
USER 10014

# Set the entrypoint to the executable
ENTRYPOINT ["/app/sub2clash"]