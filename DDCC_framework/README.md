

---

# DDCC_framework

The DDCC_framework is an interface implementation for developing TCP congestion control algorithms in user space, based on netlink technology.

The DDCC_framework implements the function of sending state samples collected by the kernel (such as sending rate, latency) to the redis channel (rlccstate\\*{flag}: flag is the stream ID automatically assigned by the module), and transmitting the congestion parameters you want to set (cwnd, pacing_rate) to the kernel module through the redis channel (rlccaction\\_{flag}), enabling automatic configuration by the kernel module.

## Project Components:

- Executor.c : Executor kernel module
- Forwarder.c : User space forwarding program, intermediary communication between kernel and redis
- load.sh : Startup script
- rmmod.sh : Module removal script

## Usage:

```bash
make all : Compile all
make module : Compile the kernel module
make user : Compile the forwarding program
make clean : Clean up compilation results
```

## Compilation Dependencies:

- libhiredis: Redis C language client
- pthread: Multithreading library

## Runtime Dependencies:

- redis: apt install redis-server

---
