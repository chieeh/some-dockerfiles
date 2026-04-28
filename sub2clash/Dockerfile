FROM alpine:latest
RUN addgroup -g 10014 choreo && \
    adduser -D -u 10014 -G choreo -s /bin/sh -h /home/choreo choreo
WORKDIR /home/choreo
COPY --chown=10014:10014 --from=ghcr.io/bestnite/sub2clash:latest /app/sub2clash ./sub2clash
RUN chmod -R 777 /home/choreo && chmod +x /home/choreo/sub2clash
# Use the above created unprivileged user
USER 10014
RUN mkdir /home/choreo/data

# Set the entrypoint to the executable
ENTRYPOINT ["./sub2clash"]