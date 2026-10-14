ARG GO_IMAGE_NAME
ARG GO_IMAGE_VERSION

FROM ${GO_IMAGE_NAME}:${GO_IMAGE_VERSION}

WORKDIR /app
ENV GOPROXY=https://mirrors.aliyun.com/goproxy,direct
RUN go install github.com/air-verse/air@latest

COPY go.mod go.sum ./
# RUN go mod download

COPY . .

EXPOSE 8080 8081 8091

CMD ["air", "-c", "/app/.air/.air.auth.toml"]
