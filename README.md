# SNLI-decomposable-attention
Decomposable Attention Model for Sentence Pair Classification (Pytorch Version) from paper 'A Decomposable Attention Model for Natural Language Inference' https://arxiv.org/abs/1606.01933

use the preprocessing python code from https://github.com/harvardnlp/decomp-attn to generate hdf5 data files.

note: the harvard code has some typos in their read me. Also they expect python 2.7 only.


note to self:

There is a conda environment in clara called : `decompattn_nonallennlp`

Have installed pytorch on this environment using :

`conda install pytorch torchvision cudatoolkit=8.0 -c pytorch`

after downloading snli and glove these are the two commands i ran in harvward code :

```
python preprocess.py --srcfile outputs/src-train.txt --targetfile outputs/targ-train.txt --labelfile outputs/label-train.txt --srcvalfile outputs/src-dev.txt --targetvalfile outputs/targ-dev.txt --labelvalfile outputs/label-dev.txt --srctestfile outputs/src-test.txt --targettestfile outputs/targ-test.txt --labeltestfile outputs/label-test.txt --outputfile outputs/hdf5 --glove data/glove/glove.840B.300d.txt
```

```
python get_pretrain_vecs.py --dictionary outputs/hdf5.word.dict --glove data/glove/glove.840B.300d.txt --outputfile outputs/glove.hdf5
```


once you have the hdf5 files, 

- switch back to python 3.7
- you can run this snli training code from `libowen` using
```
python train_baseline_snli.py --train_file data/hdf5-train.hdf5 --dev_file data/hdf5-val.hdf5 --test_file data/hdf5-test.hdf5 --w2v_file data/glove.hdf5 --log_dir logs/ --gpu_id 0 --log_fname mithunlog.log
```