# OpenSSL EVP的使用

这个项目通过调用OpenSSL EVP中的密码学函数，实现了以下四个功能：

1. 对称加密算法`EVP_AES_256_*`的密钥生成，加密与解密功能；
2. 信息摘要功能；
3. 非对称加密RSA密钥的生成与保存，加密与解密功能；
4. 数字签名功能（使用RSA密钥对）；

## EVP简介

Openssl [EVP](https://blog.csdn.net/liao20081228/article/details/76285896) (high-level cryptographic functions) 提供了丰富的密码学中的各种函数。Openssl中实现了各种对称算法、摘要算法以及签名/验签算法。EVP函数将这些具体的算法进行了封装。

EVP函数位于OpenSSL 中的 [libcrypto](https://github.com/openssl/openssl) 库，它是一个功能齐全的通用加密库，构成了 TLS 实现的基础，但也可以独立使用。

## 项目使用

目录介绍：

> `include`——OpenSSL的头文件
>
> `lib`——libcrypto库的依赖项
>
> `bin`——libcrypto库需要的动态链接库
>
> `src`——本项目功能的源文件
>
> `Debug`——可直接运行`UseOfOpennSSLEVP.exe`，运行结果是src文件夹下main函数实现的功能，验证了每个加密解密以及密钥保存等功能是否可用。

在Visual Studio 中运行时，需要添加`C/C++ -> 高级 -> 禁用特定警告 -> 4996`，因为使用了OpenSSL 准备弃用的函数

## 参考资料

* [Windows下配置OpenSSL](https://blog.csdn.net/zhaitianbao/article/details/120224131)
* [[OpenSSL RSA Encryption/Decryption with EVP Methods](https://stackoverflow.com/questions/70535625/openssl-rsa-encryption-decryption-with-evp-methods)
* [OpenSSL EVP PKEY Encrypt and Decrypt](https://www.youtube.com/watch?v=e9As9Hopn0E)
* [OpenSSL中文手册之EVP库详解](https://blog.csdn.net/liao20081228/article/details/76285896)
* [Win32/Win64 OpenSSL Installer for Windows - Shining Light Productions (slproweb.com)](https://slproweb.com/products/Win32OpenSSL.html)

