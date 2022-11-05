# Starting with the image that we'll use for building.
# It is big (352 mb) based on the very small alpine(5.54 mb), but with all golang needed stuff.
FROM golang:1.19.3-alpine3.16 AS yosef

# next, set a working directory for the following commands:
WORKDIR /app

# copy just the go.mod file from the current directory in my working host to WORKDIR in the image.
COPY go.mod ./

# run the "go mod download" command, so that go will download dependencies into the image.
RUN go mod download

# copy all go files into the WORKDIR
COPY *.go ./

# Compile go source and create an executable file in this destination directory in the image
# could use the WORKDIR, but didn't this time
RUN go build -o /app/webdemo

## Deploy
# We are using a new very small clean Alpine image, and we'll copy just the single executable file!!!
FROM alpine:3.16.2

WORKDIR /

# I have used a stupid name for the build image, so that you'll know you don't have to use a 
# specific name like "build".
# ..so copy the single "webdemo" executable file into the current directory "."
# (that is the root directory as we have used the WORKDIR before)
COPY --from=yosef /app/webdemo .

# This one is actually does nothing really - it serve as a communication to the guy that will
# be running this, to let him know that the image will listen on this port.
# (so he better use "-p 8080:8080" or something simmilar when running)
EXPOSE 8080

# so this is the command when we run it.
ENTRYPOINT ["/webdemo"]