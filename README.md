# SNLI-decomposable-attention
Decomposable Attention Model for Sentence Pair Classification (Pytorch Version) from paper 'A Decomposable Attention Model for Natural Language Inference' https://arxiv.org/abs/1606.01933

use the preprocessing python code from my fork of harvard code
 `https://github.com/mithunpaul08/decomp-attn`
to generate hdf5 data files.



once you have the hdf5 files, 

- switch back to python 3.7
- you can run this snli training code from `libowen` using
```
python train_baseline_snli.py --train_file data/hdf5-train.hdf5 --dev_file data/hdf5-val.hdf5 --test_file data/hdf5-test.hdf5 --w2v_file data/glove.hdf5 --log_dir logs/ --gpu_id 0 --log_fname mithunlog.log
```