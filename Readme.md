**Add WhiteSU support to your Non-GKI kernel!**

WhiteSU supports integration into Non-GKI kernels that lack LKM module support (specifically Linux kernel versions 4.14 and older); such kernels require integration via *manual hooks*. How does it work?
You take the source code for your target kernel and modify specific files—specifically, you insert function *hooks* to enable root functionality. So, how do you integrate it into the kernel?

First, we need the installer.
```shell
curl -LSs "https://raw.githubusercontent.com/White-Society/WhiteSU/dev/kernel/setup.sh" | bash -s legacy
```

Next, apply the necessary modifications to the kernel source code; you can use the provided patches for this:
https://github.com/White-Society/kernel-patches/tree/whitesu/syscall_hook
```shell
cd /patch/to/kernel/
patch -p1 < /patch/to/kernel-patches-whitesu/syscall_hook/syscall_hook_4.14.patch
```

If the patches apply successfully, go ahead and build the kernel; once the build is complete, you will have a kernel with WhiteSU functionality enabled!


**RU: Добавьте поддержку WhiteSU в свое Non-GKI ядро!**

WhiteSU поддерживает интеграцию в Non-GKI ядро, у которых отсутвует поддержка LKM модулей, такими ядрами является версия Linux, ниже 4.14 включительно, для таких ядер требуется интеграция путем *ручными хуками.* Как это работает?
Вы берете исходный код нужного вашего ядра, далее делаете исправления в некоторых файлах, а именно вы прописываете *перехваты* функций, для работы самих рут прав. Итак, как интегрировать ядро?

Для начала нам нужен установщик.
```shell
curl -LSs "https://raw.githubusercontent.com/White-Society/WhiteSU/dev/kernel/setup.sh" | bash -s legacy
```

После чего делаем исправления в исходном коде ядра, для этого можно воспользоваться готовыми патчами
https://github.com/White-Society/kernel-patches/tree/whitesu/syscall_hook
```shell
cd /patch/to/kernel/
patch -p1 < /patch/to/kernel-patches-whitesu/syscall_hook/syscall_hook_4.14.patch
```

Если патчи встали, то смело запускайте сборку ядра, после сборки вы получите ядро с работающим WhiteSU!