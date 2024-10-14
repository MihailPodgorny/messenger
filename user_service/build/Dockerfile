# MULTI STAGE EXAMPLE
ARG BASE_IMAGE_REGISTRY

#######################################
# STAGE 1. BUILD STAGE
#######################################

# FROM ${BASE_IMAGE_REGISTRY}/golang/build:1.21-alpine3.19 AS build # Like Big Tech
FROM ${BASE_IMAGE_REGISTRY}/golang:1.22-alpine3.19 AS build

WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download

COPY *.go ./
RUN CGO_ENABLED=0 GOOS=linux go build -o /bin/main ./cmd/user/main.go

#######################################
# STAGE 2. FINAL STAGE
#######################################

FROM scratch  AS final

WORKDIR /

COPY --from=build /bin/main /main

EXPOSE 8080

ENTRYPOINT ["/main"]