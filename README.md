# mnist-ain
An MNIST code repository for [`AI Network`](https://ainetwork.ai/). The source code is originated in [`github.com/pytorch/examples`](https://github.com/pytorch/examples) and was modified for our purpose. For the full context of the code, see the original code repository.

## How to run on [`AIN Cloud beta`](https://cloud.ainetwork.ai/)

*See [`AIN.md`](https://github.com/ainblockchain/mnist-ain/blob/master/AIN.md) for a guide to play with the code on [`AIN Cloud beta`](https://cloud.ainetwork.ai/), which is a product provided by [`AI Network`](https://ainetwork.ai/).*

## How to run using commandlines

It can be run in [`Docker`](https://docs.docker.com/) containers using the commandlines below. 
For the details about the arguments, see [`github.com/anibali/docker-pytorch`](https://github.com/anibali/docker-pytorch).

### Run w/ pytorch docker image (on CPU machine): 

```bash
docker run --rm -t \
  -v=$PWD/mnist:/mnist \
  -w /mnist \
  anibali/pytorch:no-cuda \
  python3 /mnist/main.py \
  --epochs=1
```

### Run w/ pytorch docker image (on GPU machine): 

```bash
docker run --rm -t \
  -v=$PWD/mnist:/mnist \
  -w /mnist \
  --runtime=nvidia \
  -e NVIDIA_VISIBLE_DEVICES=0 \
  anibali/pytorch:cuda-9.0 \
  python3 /mnist/main.py \
  --epochs=1 
```
