# Quarry

Alternative client software for mining Monero with P2Pool.

## Status

Quarry can mine on a [P2Pool](https://github.com/SChernykh/p2pool) node through its stratum
server, like XMRig does. Running as a P2Pool node itself is still a work in progress.

## Mining on P2Pool

Start P2Pool with your wallet address (payouts go to the wallet P2Pool was started with), then
point Quarry at its stratum port:

```bash
quarry --pool 127.0.0.1:3333
```

Options:

- `--threads N`: mining threads (default: one per CPU)
- `--light`: RandomX light mode, using 256 MiB instead of ~2.3 GiB, but much slower
- `--user NAME`: worker name shown by P2Pool; `NAME+DIFF` requests a fixed share difficulty

Build with `zig build --release=fast` for full hashing speed. Mining needs an x86-64 CPU with
AES-NI.

## Documentation

See the `docs` folder.

Build instructions are available [here](docs/BUILD.md).
