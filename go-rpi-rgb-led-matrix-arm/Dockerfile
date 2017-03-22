FROM mcuadros/docker:1.8-0-alpine

RUN apk add --no-cache git make gcc g++ && \
    mkdir -p $GOPATH/src/github.com/mcuadros && \
    git clone https://github.com/mcuadros/go-rpi-rgb-led-matrix.git \
        $GOPATH/src/github.com/mcuadros/go-rpi-rgb-led-matrix && \
    cd $GOPATH/src/github.com/mcuadros/go-rpi-rgb-led-matrix/vendor/rpi-rgb-led-matrix/ && \
    git submodule update --init && \
    make && \
    cd $GOPATH/src/github.com/mcuadros/go-rpi-rgb-led-matrix/ && \
    go get -v ./... && \
    go install -v ./...

WORKDIR $GOPATH/src/github.com/mcuadros/go-rpi-rgb-led-matrix
