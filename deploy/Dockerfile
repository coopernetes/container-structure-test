FROM golang:1.19
ADD https://github.com/GoogleCloudPlatform/docker-credential-gcr/releases/download/v2.1.6/docker-credential-gcr_linux_amd64-2.1.6.tar.gz /usr/local/bin
RUN tar -C /usr/local/bin/ -xvzf /usr/local/bin/docker-credential-gcr_linux_amd64-2.1.6.tar.gz

FROM gcr.io/distroless/base:latest
COPY --from=0 /usr/local/bin/docker-credential-gcr /docker-credential-gcr
ADD out/container-structure-test-linux-amd64 /container-structure-test
ENTRYPOINT ["/container-structure-test"]
