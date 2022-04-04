# KAS demo

## Build

We use `kas`, a wrapper around Yocto/bitbake and replacement for the "old"
Google Repo tool): <https://kas.readthedocs.io/en/latest/intro.html>

It comes in two flavors, one of them is a fully Dockerized build environment,
which we use here. So running a build boils down to executing the following
command:

    ./kas-container build bd-nitrogen8m-multimedia-full.yml

If you want to use a shared state cache, set `SSTATE_DIR` when running
`kas-container`, it will pick up the environment variable and pass it through
into the Docker container.

For example:

    DL_DIR="<your_shared_dl_dir>" SSTATE_DIR="<your_shared_sstate_dir>" \
    ./kas-container build bd-nitrogen8m-multimedia-full.yml

## SDK

Build the SDK with

    ./kas-container shell -c 'bitbake boundary-image-multimedia-full -c populate_sdk' bd-nitrogen8m-multimedia-full.yml

## Authors

Simon Kuhnle <simon.kuhnle@methodpark.de>
Stephan Linz <stephan.linz@navimatix.de>

