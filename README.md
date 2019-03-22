# SNLI-decomposable-attention
Decomposable Attention Model for Sentence Pair Classification (Pytorch Version) from paper 'A Decomposable Attention Model for Natural Language Inference' https://arxiv.org/abs/1606.01933

use the preprocessing python code from https://github.com/harvardnlp/decomp-attn to generate hdf5 data files.

note: the harvard code has some typos in their read me. Also they expect python 2.7 only.


note to self:

There is a conda environment in clara called : `decompattn_nonallennlp`

Have installed pytorch on this environment using :

`conda install pytorch torchvision cudatoolkit=8.0 -c pytorch`

after downloading snli and glove this is the command i ran in harvward code :

```
python preprocess.py --srcfile outputs/src-train.txt --targetfile outputs/targ-train.txt --labelfile outputs/label-train.txt --srcvalfile outputs/src-dev.txt --targetvalfile outputs/targ-dev.txt --labelvalfile outputs/label-dev.txt --srctestfile outputs/src-test.txt --targettestfile outputs/targ-test.txt --labeltestfile outputs/label-test.txt --outputfile outputs/hdf5 --glove data/glove/
```

```
python get_pretrain_vecs.py --dictionary outputs/hdf5.word.dict --glove data/glove/glove.840B.300d.txt --outputfile data/glove.hdf5
```


once you have the hdf5 files, you can run this code using
`python train_baseline_snli.p`