# Kealib

Built using msys2 with rtools compilers. Includes:

 - `kealib 1.4.7`
 - `hdf5 1.8.20`

hdf5 was built from `mingw-w64-hdf5` + rtools. To build kea:

```sh
wget https://bitbucket.org/chchrsc/kealib/downloads/kealib-1.4.7.tar.gz
tar xzvf kealib-1.4.7.tar.gz
cd kealib-1.4.7/trunk
cmake -G"MSYS Makefiles" . -DBUILD_SHARED_LIBS=OFF -DCMAKE_INSTALL_PREFIX="/usr/local" 
sed -i 's/-lhdf5_cpp/-lhdf5_cpp -lhdf5 -lszip -lz' src/CMakeFiles/test1.dir/build.make
make
```

And to install to `/usr/local` run:

```
make install
```
