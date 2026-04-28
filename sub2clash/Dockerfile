FROM alpine:latest
RUN addgroup -g 10014 choreo && \
    adduser -D -u 10014 -G choreo -s /bin/sh -h /home/choreo choreo
WORKDIR /home/choreo
COPY --chown=choreo:choreo --from=ghcr.io/bestnite/sub2clash:latest /app/sub2clash ./sub2clash
RUN chmod +x ./sub2clash
# Use the above created unprivileged user
USER 10014

# Set the entrypoint to the executable
ENTRYPOINT ["./sub2clash"]