# Plumed

To [download](https://www.plumed.org/download), configure, build, and install [Plumed](https://github.com/plumed/plumed2/releases/latest)&#160;2.x (CP2K requires Plumed2), one may proceed as shown below. See also [How to compile CP2K with Plumed](https://www.cp2k.org/howto:install_with_plumed).

```bash
wget --no-check-certificate https://github.com/plumed/plumed2/archive/v2.6.1.tar.gz
tar xvf v2.6.1.tar.gz
cd plumed2-2.6.1

wget --no-check-certificate https://github.com/hfp/xconfigure/raw/master/configure-get.sh
chmod +x configure-get.sh
./configure-get.sh plumed
```

Please make the intended compiler available on the command line. For instance, many HPC centers rely on `module load`.

```bash
source /opt/intel/compilers_and_libraries_2020.2.254/linux/bin/compilervars.sh intel64
```

For example, to configure and make for an Intel Xeon Scalable processor ("SKX"):

```bash
make distclean
./configure-plumed-skx.sh
make -j; make install
```

## References

[https://github.com/plumed/plumed2/releases/latest](https://github.com/plumed/plumed2/releases/latest)  
[https://www.cp2k.org/howto:compile#o_plumed_optional_enables_various_enhanced_sampling_methods](https://www.cp2k.org/howto:compile#o_plumed_optional_enables_various_enhanced_sampling_methods)  
[https://www.cp2k.org/howto:install_with_plumed](https://www.cp2k.org/howto:install_with_plumed)  
[https://www.plumed.org/](https://www.plumed.org/)

