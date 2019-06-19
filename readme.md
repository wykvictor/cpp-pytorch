## The project is self-contained

* libtorch is the pytorch 1.1 libtorch download from [link](https://download.pytorch.org/libtorch/cpu/libtorch-macos-1.1.0.zip)
* add libmklml.dylib and libiomp5.dylib to libtorch/lib in case missing these depends
* install pytorch 1.1: conda install pytorch torchvision -c pytorch
* https://pytorch.org/tutorials/advanced/cpp_export.html

## cpp-pytorch
PyTroch 1.1 preview - LOADING A PYTORCH MODEL IN C++

Details refer to: https://zhuanlan.zhihu.com/p/45981883

Main requires: PyTroch 1.1(used to run python tracing.py), opencv, cmake

### STEP 1
CONVERTING YOUR PYTORCH MODEL TO TORCH SCRIPT and SERIALIZING YOUR SCRIPT MODULE TO A FILE

- run `python tracing.py` and get `model.pt`

### STEP 2
LOADING YOUR SCRIPT MODULE IN C++ and EXECUTING

1. Download LibTorch [here](https://pytorch.org/) and unzip

2. Cmake
```
mkdir build
cd build
cmake ..
make
```

3. Run demo
```
./example-app ../model.pt ../dog.png ../synset_words.txt
```

Input image and predicted label: `n02108422 bull mastiff`, bingo!

![](dog.png)

