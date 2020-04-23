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

OH, no, duh - this is alot more complicated

looking into the example dockerfiles, they have qemu-<platform> inserted into plarform specific base images, to run _that_ inside each hub build

and also unmentioned, is that each dockerfile thus needs to be configured separately in DockerHub.

really not user friendly, what we really need, is something more clever.

And no, that's not what I want.

I _want_ to be able to have one Dockerfile, and build for a list of arches - just like Rancher/dapper...

## So going back to a `Dockerfile`, and looking at github actions...

cos they have matrix builds..
