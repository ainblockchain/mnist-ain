# mnist-ain
MNIST code for AI Network demo. See [`github.com/pytorch/examples`](https://github.com/pytorch/examples) for the full context of the MNIST code.

## How to run using commandlines

It can be run in [`Docker`](https://docs.docker.com/) containers using the commandlines below. 
For the details about the arguments, see [`github.com/anibali/docker-pytorch`](https://github.com/anibali/docker-pytorch).

### Run w/ pytorch docker image (on CPU machine): 

```bash
docker run --rm -it --init \
  --ipc=host \
  --user="$(id -u):$(id -g)" \
  -v=$PWD:/mnist \
  -w /mnist \
  anibali/pytorch:no-cuda \
  python3 main.py 
```

### Run w/ pytorch docker image (on GPU machine): 

```bash
docker run --rm -it --init \
  --ipc=host \
  --user="$(id -u):$(id -g)" \
  -v=$PWD:/mnist \
  -w /mnist \
  --runtime=nvidia \
  -e NVIDIA_VISIBLE_DEVICES=0 \
  anibali/pytorch:cuda-9.0 \
  python3 main.py
```
