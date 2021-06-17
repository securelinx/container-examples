FROM opensuse/leap:15.2 as builder

RUN zypper -n in gcc glibc-devel-static

WORKDIR /tmp/builder
COPY hello.c ./
RUN gcc -static -o hello hello.c

FROM scratch
COPY --from=builder /tmp/builder/hello /
CMD ["/hello"]
