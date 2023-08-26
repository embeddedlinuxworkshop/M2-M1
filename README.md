
## 1. Toolchain.

-----

## Pre-Requisites for Session
---

```shell
sudo apt-get install autoconf automake bison bzip2 cmake 
sudo apt-get install flex g++ gawk gcc gettext git gperf help2man 
sudo apt-get install libncurses5-dev libstdc++6 libtool libtool-bin make
sudo apt-get install patch python3-dev rsync texinfo unzip wget xz-utils
```


```shell
git clone https://github.com/crosstool-ng/crosstool-ng.git
cd crosstool-ng
./bootstrap
./configure --prefix=${PWD}
make
make install
```
---

## Keywords.

1. Toolchain.
2. crosstool-NG.
3. static library.
4. Dynamic Library.
5. cross compiling.
6. Native
7. Cross.
8. Host.
9. Target.

---
## Actions.

1. Finding a toolchain.
2. Building a toolchain.
3. Understand what is inside Toolchain.
4. cross-compiling.
5. Extract Main Runtime Linker from a binary.
6. Extract `Shared Library` from a binary.
7. Explain what is `Shared Library` ?
8. Explain what is `Static Library` ?
9. Compile your code with a Shared Library.
10. Compile your code with Static Library.
11. Create a `Static Library`
12. Create `Dynamic Library`
---

## 1. Finding a Toolchain.

- Pre-built.
- Manual compiling through crossTOOLNG.

```shell
bin/ct-ng disclean
bin/ct-ng list-samples
bin/ct-ng <choose sample>
bin/ct-ng menuconfig
bin/ct-ng build

# output path: ~/x-tools
```

## 2. Building a Toolchain.

- Using crossNG to build a toolchain for raspi3.

---
## 3. Understand what are inside Toolchain ?

- ![alt text](https://github.com/embeddedlinuxworkshop/M2-M1/blob/main/1.%20Toolchain.png)
---

## 4. Cross Compiling.

- cross compile application for raspi3.


## 5. Best practices for organizing your workflow.

- alias.
- .bashrc for PATH.
---

## 6. Extract Main Runtime Linker from a binary.

- ldd tool.
- readelf + grep.
## 7. Extract Shared Library from a binary.

- ldd tool.
- readelf + grep.
---

## 9. Create static library.

```shell
aarch64-rpi3-linux-gnu-g++  -c <cpp_file>.cpp
aarch64-rpi3-linux-gnu-ar rc lib<name>.a <objects>.o ...
```

## 10. Create a shared library.

```
aarch64-rpi3-linux-gnu-g++ -fPIC -c <cpp file>
aarch64-rpi3-linux-gnu-g++ -shared -o output.so <object1>.o <object2>.o
```
---

## 11. Compile your code with a shared Library

```shell
aarch64-rpi3-linux-gnu-g++ <main_program>.cpp -loutput
```

## 12. Compile Your code with Static Library.

```
aarch64-rpi3-linux-gnu-g++ <main_program>.cpp -loutput
```


---





