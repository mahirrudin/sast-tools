# Secret Scanner
FROM python:3-alpine
RUN apk add --no-cache git && pip install trufflehog

# Add non-root user 
RUN addgroup -S redteam && \
    adduser -S -G redteam redteam && \
    mkdir -p /app/ 

USER redteam
WORKDIR /app/

ENTRYPOINT ["trufflehog", "--json", "file:///app"]
