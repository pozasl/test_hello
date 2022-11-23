# Testing repo for cross compile container

## Requirements
- docker
- binfmt-support
- qemu-user-static

## BUILD the project using the cross-compile container
```bash
docker run -it --user $(id -u):$(id -g) --rm --volume `pwd`:/home/default/workdir lpozas/cross-compile-container:arm64
```

## RUN the result binaries in the cross-compile container:
```bash
docker run --user root -it --rm --volume `pwd`:/home/default/workdir lpozas/cross-compile-container:arm64
cp /home/default/wordir/build/hello /rpi4-bullseye-arm64/
chroot /rpi4-bullseye-arm64/
./hello
```