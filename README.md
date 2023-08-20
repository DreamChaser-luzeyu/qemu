# QEMU

官方文档 [跳转](README.rst)
个人学习笔记 [跳转](notes.md)

## 编译安装
安装依赖
```bash
sudo apt-get install git libglib2.0-dev libfdt-dev libpixman-1-dev zlib1g-dev ninja-build
```
配置
```bash
mkdir build && cd build
# 编译全部体系架构
../configure
# 编译指定体系架构
# --target-list=LIST       set target list (default: # build all)
#                            Available targets: # aarch64-softmmu # alpha-softmmu 
#                            arm-softmmu avr-softmmu # cris-softmmu hppa-softmmu 
#                            i386-softmmu # loongarch64-softmmu # m68k-softmmu 
#                            microblaze-softmmu # microblazeel-softmmu # mips-softmmu 
#                            mips64-softmmu # mips64el-softmmu # mipsel-softmmu 
#                            nios2-softmmu or1k-softmmu # ppc-softmmu ppc64-softmmu 
#                            riscv32-softmmu # riscv64-softmmu rx-softmmu 
#                            s390x-softmmu sh4-softmmu # sh4eb-softmmu 
#                            sparc-softmmu # sparc64-softmmu # tricore-softmmu 
#                            x86_64-softmmu # xtensa-softmmu # xtensaeb-softmmu 
#                            aarch64-linux-user # aarch64_be-linux-user 
#                            alpha-linux-user # arm-linux-user # armeb-linux-user 
#                            cris-linux-user # hexagon-linux-user # hppa-linux-user 
#                            i386-linux-user # loongarch64-linux-user 
#                            m68k-linux-user # microblaze-linux-user 
#                            microblazeel-linux-user # mips-linux-user 
#                            mips64-linux-user # mips64el-linux-user 
#                            mipsel-linux-user # mipsn32-linux-user 
#                            mipsn32el-linux-user # nios2-linux-user 
#                            or1k-linux-user # ppc-linux-user # ppc64-linux-user 
#                            ppc64le-linux-user # riscv32-linux-user 
#                            riscv64-linux-user # s390x-linux-user # sh4-linux-user 
#                            sh4eb-linux-user # sparc-linux-user 
#                            sparc32plus-linux-user # sparc64-linux-user 
#                            x86_64-linux-user # xtensa-linux-user 
#                            xtensaeb-linux-user
../configure --prefix=$(pwd) \
             --target-list=riscv32-linux-user \
             --target-list=riscv64-linux-user \
             --enable-debug
```
编译并生成compilation_db.json
```bash
bear -- make -j14
```
最后可以在build目录下找到生成的二进制文件。