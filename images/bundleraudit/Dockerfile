# SCA for Ruby - Bundler Audit
FROM ruby:alpine
RUN gem install bundler-audit

# Add non-root user 
RUN addgroup -S redteam && \
    adduser -S -G redteam redteam && \
    mkdir -p /app/ 

USER redteam
WORKDIR /app/

ENTRYPOINT ["bundler-audit"]
