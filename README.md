# singularity-sl6-uboonecode

This repo contains a script for building a uboonecode container.

It uses `pullProducts`, a script that untars binaries for a specific uboonecode version into a folder in the container, `/products`.

To build the version of your choice, go into the file, `Singularity`, and change the line

    ./pullProducts /products slf6 uboone-v06_26_01_14 e10 prof


Note, this applies to other sci-soft products as well. List of products [here](http://scisoft.fnal.gov/). 

Once in the container, you can set it up and run `lar` by

```
source /products/setup
setup uboonecode [version] -q [qualifier]
```

You can also develop with the container!!!

To setup an MRB build environment for the first time (for uboonecode):

```
source /products/setup
setup uboonecode [version] -q [qualifier]

mkdir [my build dir]
cd [my build dir]

setup mrb
export MRB_PROJECT=larsoft
mrb newDev
source localProducts-xxxxxx/setup
cd srcs
mrb g uboonecode

mrbsetenv
```


### Notes

* As of 4/23/18, building a uboonecode image was about 3.9 GB.
* eventdump.fcl works
* running DL_br branch to make larcv files work!