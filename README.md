# multi-arch
where are the docs?

https://github.com/ckulka/docker-multi-arch-example is interesting - multi-arch docker images, built entirely on docker hub

BUT - the repo uses one dockerfile per arch, and a filename that i can't find docs for... so i'm curious..

## what's the minimum to build more than one arch?

Can I just add the `hook/pre_build`, and a single Dockerfile?

NOPE - Docker hub loads the hook, but then builds the Dockerfile as amd64

## will adding a `arm32v7.dockerfile` build 2 archs?


NOPE, looks to me like if there is a `Dockerfile` then Hub just build amd64

## rename `Dockerfile` to `amd64.dockerfile`

