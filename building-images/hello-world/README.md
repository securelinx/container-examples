To build this example container run:

    zypper in gcc glibc-devel-static
    gcc -static -o hello hello.c
    docker build .
