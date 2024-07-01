# Introduction
The deploy directory is the deploy component
The gym_rlcc directory is the standard gym environment implemented
The train_code directory is the training component
The train_env_tcp directory is Network Simulation Component
The DDCC_framework directory contains the executor and forwarder.
---

## Environment Configuration

All use python3

### deploy:

```bash
apt install redis-server
pip3 install numpy redis
```

### gym_rlcc:

```bash
cd gym_rlcc
pip3 install -e .
```

### DDCC_framework:

```bash
apt install redis-server
# install hiredis
wget https://github.com/redis/hiredis/archive/refs/tags/v1.0.2.tar.gz
tar -xf v1.0.2.tar.gz
cd hiredis-1.0.2/
make
make install

cd DDCC_framework
make all
```

### train_code:

```bash
pip3 install numpy redis
# Install gym_rlcc
```

### train_env_tcp

```bash
apt install redis-server
# Install mininet
https://zhuanlan.zhihu.com/p/576832894

pip3 install streamlit redis
```

## How to train DDCC

1. Mount DDCC_framework

```bash
cd DDCC_framework
sudo bash load.sh
```

2. Start training environment

```bash
cd train_env_tcp
sudo python3 train_env_tcpnl.py
```

3. Train

```bash
cd train_code
python3 train_rlcc.py
```

## How to deploy DDCC

1. Mount DDCC_framework

```bash
cd DDCC_framework
sudo bash load.sh
```

2. Deploy

```bash
cd deploy
python3 deploy.py
```

## How to visualize in real-time

```bash
cd train_env_tcp/webui
streamlit run app.py
```

---
