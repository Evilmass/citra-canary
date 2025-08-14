bass off [Canary #2773](0709663316bdb2a66490cf7dbf591cfb02d89d16)

```shell
git clone --recursive https://github.com/Evilmass/citra-nightly

# fix vk_device_info.obj : error LNK2001: 无法解析的外部符号 "class vk::detail::DispatchLoaderDynamic vk::detail::defaultDisp
set VULKAN_SDK=

# msvc 2019
cmake --fresh -S . -B build -G "Visual Studio 17 2022" -A x64 -T v142 -DCMAKE_POLICY_VERSION_MINIMUM=3.5 -DCMAKE_BUILD_TYPE=Release -DENABLE_QT_TRANSLATION=ON -DCITRA_ENABLE_COMPATIBILITY_REPORTING=OFF -DUSE_DISCORD_PRESENCE=OFF
msbuild build/citra.sln -m -p:Configuration=Release,Platform=x64 -t:Rebuild

# pack
bash pack.sh build/
```

**[ORIGINAL_README](./ORIGINAL_README.md)**