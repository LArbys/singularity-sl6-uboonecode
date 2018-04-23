# singularity-sl6-uboonecode

This repo contains a script for building a uboonecode container.

It uses `pullProducts`, a script that untars binaries for a specific uboonecode version into a folder in the container, `/products`.

Once in the container, you can set it up and run `lar` by

```
source /products/setup
setup uboonecode [version] -q [qualifier]
```

You can also develop in the container!

To setup an MRB build environment for the first time:

```
source /products/setup
setup uboonecode [version] -q [qualifier]

mkdir [my build dir]
cd [my build dir]

setup mrb
export MRB_PRODUCT=larsoft
mrb newDev
source localProducts-xxxxxx/setup
cd srcs
mrb g uboonecode

mrbsetenv
```


