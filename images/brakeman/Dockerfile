# SAST for Ruby - Brakeman
FROM ruby:alpine
RUN gem install brakeman

# Add non-root user 
RUN addgroup -S redteam && \
    adduser -S -G redteam redteam && \
    mkdir -p /app/ 

USER redteam
WORKDIR /app/

ENTRYPOINT ["brakeman", "--no-exit-on-warn", "--no-exit-on-error", "--format", "json", "--output", "sast-result.json"]
