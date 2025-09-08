ARG FROM_TAG=release-alpine

FROM ghcr.io/ponylang/ponyc:${FROM_TAG}

LABEL org.opencontainers.image.source=https://github.com/redvers/pony-odbc-builder

RUN apk add --update --no-cache \
    unixodbc-dev \
    psqlodbc \
    bash \
    mariadb-connector-odbc \
    pcre2-dev \
    openssl-dev \
    zstd-static \
    openssl-libs-static \
    cmake \
    zlib-static

RUN apk --no-cache del libbz2

COPY .odbc.ini /root/


RUN wget https://github.com/tukaani-project/xz/releases/download/v5.8.1/xz-5.8.1.tar.gz
RUN tar -zxvf xz-5.8.1.tar.gz
RUN cd xz-5.8.1 && ./configure --prefix=/usr && make && make install

RUN wget https://libzip.org/download/libzip-1.11.4.tar.gz && tar -zxvf libzip-1.11.4.tar.gz
RUN cd libzip-1.11.4 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF -DCMAKE_INSTALL_PREFIX=/usr ; make ; make install
