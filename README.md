# End-to-End ASR with Listen Attend and Spell Framework
This is a PyTorch implementation of End-to-End Automatic Speech Recognition with [Listen Attend and Spell (LAS)](https://arxiv.org/abs/1508.01211v2) framework.

## Install
- PyTorch 0.4.1+
- Python3 (Recommend Anaconda)
- `pip install -r requirements.txt`
- `cd tools; make KALDI=/path/to/kaldi`
- If you want to run `egs/aishell/run.sh`, download [aishell](http://www.openslr.org/33/) dataset for free.

## Usage
1. `$ cd egs/aishell` and modify aishell data path to your path in `run.sh`.
2. `$ bash run.sh`, that's all!

You can change hyper-parameter by `$ bash run.sh --parameter_name parameter_value`.

Workflow of `egs/aishell/run.sh`:
- Stage 0: Data Preparation
- Stage 1: Feature Generation
- Stage 2: Dictionary and Json Data Preparation
- Stage 3: Network Training
- Stage 4: Decoding

If you want to visualize your loss, you can use `visdom` to do that:
- Open a new terminal in your remote server (recommend tmux) and run `$ visdom`.
- Open a new terminal and run `$ bash run.sh --visdom 1 --visdom_id "<any-string>"` or `$ train.py ... --visdom 1 --vidsdom_id "<any-string>"`.
- Open your browser and type `<your-remote-server-ip>:8097`, egs, `127.0.0.1:8097`.
- In visdom website, chose `<any-string>` in `Environment` to see your loss.
