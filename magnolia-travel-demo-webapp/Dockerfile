FROM alpine:3.12 AS builder

WORKDIR /app
COPY target/magnolia-travel-demo-webapp-*.war /app/webapp.war
RUN unzip webapp.war && \
    rm -vf webapp.war

FROM busybox:latest AS final

COPY --from=builder /app/ /magnolia/
