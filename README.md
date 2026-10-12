# Profanity SAFU

![Splash](img/splash.png)

Profanity is an Ethereum vanity address generator originally built by [johguse](https://github.com/johguse) and later fixed and productionized by [Juu17](https://github.com/juu17). It leverage GPU acceleration via OpenCL via a plain algorithm to generates vanity addresses in parallel efficiently.

## Security

The original Profanity seeded a 256-bit private key from only 32 bits of entropy, so every address it produced was brute-forceable ([1inch disclosure](https://blog.1inch.io/a-vulnerability-disclosed-in-profanity-an-ethereum-vanity-address-tool-68ed7455fc8c), [Amber Group write-up](https://medium.com/amber-group/exploiting-the-profanity-flaw-e986576de7ab)). This fork draws the full 256-bit seed directly from the OS CSPRNG, removing that collapse.

**Attention!**

Do NOT run the release binary on **Windows**, because there is no built-in entropy pool for getting random-enough numbers. The key random-number generator `std::random_device` falls back to a pseudorandom source on some Windows toolchains, which will bring vulnerable private keys in front of you. Build and run on macOS or Linux, where `std::random_device` is backed by the operating system's entropy pool. The build additionally refuses to compile on MinGW libstdc++ before GCC 9.2, where this fallback is known to occur.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

See [LICENSE](LICENSE).
