# LIBXC

To [download](https://gitlab.com/libxc/libxc/-/releases), configure, build, and install [LIBXC](http://www.tddft.org/programs/libxc)&#160;2.x, 3.x, or 4.x (CP2K requires LIBXC&#160;4.x and version 5.x is currently not supported), one may proceed as shown below. Please note that CP2K&#160;5.1 (and earlier) is only compatible with LIBXC&#160;3.0 (or earlier, see also [How to compile the CP2K code](https://www.cp2k.org/howto:compile#k_libxc_optional_wider_choice_of_xc_functionals)). Post-5.1, only the latest major release of LIBXC (by the time of the CP2K-release) is supported (e.g., LIBXC&#160;4.x).

```bash
wget --content-disposition http://www.tddft.org/programs/libxc/down.php?file=4.3.4/libxc-4.3.4.tar.gz
tar xvf libxc-4.3.4.tar.gz
cd libxc-4.3.4

wget --no-check-certificate https://github.com/hfp/xconfigure/raw/master/configure-get.sh
chmod +x configure-get.sh
./configure-get.sh libxc
```

Please make the Intel Compiler available on the command line. This depends on the environment. For instance, many HPC centers rely on `module load`.

```bash
source /opt/intel/compilers_and_libraries_2020.2.254/linux/bin/compilervars.sh intel64
```

For example, to configure and make for an Intel Xeon Scalable processor ("SKX"):

```bash
make distclean
./configure-libxc-skx.sh
make -j; make install
```

**NOTE**: Please disregard messages during configuration suggesting `libtoolize --force`.

## References

[https://www.cp2k.org/howto:compile#k_libxc_optional_wider_choice_of_xc_functionals](https://www.cp2k.org/howto:compile#k_libxc_optional_wider_choice_of_xc_functionals)

