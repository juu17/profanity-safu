# Profanity SAFU Version

Profanity is an Ethereum vanity address generation tool. It generates addresses in parallel by exploiting GPU power with OpenCL through a simple algorithm.

## 2022-11-15

Vulnerabilities were fixed by Juu17

**Attention!**

Do NOT run this binary on **Windows** because there is no built-in entropy pool for getting random enough numbers. The key random number generator function _random_device_ calls _random_s_(pseudorandom), that will bring vulnerable private keys in front of you.

## 2022-09-15

All affected binaries have been removed to prevent further unsafe use of this tool, please see the following article for more information:

https://blog.1inch.io/a-vulnerability-disclosed-in-profanity-an-ethereum-vanity-address-tool-68ed7455fc8c

## 2022-09-15

As per issue 76 (https://github.com/johguse/profanity/issues/76) I've decided to also archive this repository to further reduce risk that someone uses this tool. The code will not recieve any updates and I've left it in an uncompilable state. Use something else!
