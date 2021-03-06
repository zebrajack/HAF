## Train

All the training details (hyper-parameters, trained layers, backbones, etc.) strictly follow the original MatConvNet version of NetVLAD and SARE. 

The default scripts adopt 4 GPUs (require ~11G per GPU) for training, where each GPU loads one tuple (anchor, positive(s), negatives).
+ In case you want to fasten training, enlarge `GPUS` for more GPUs, or enlarge the `--tuple-size` for more tuples on one GPU;
+ In case your GPU does not have enough memory (e.g. <11G), reduce `--neg-num` for fewer positives or negatives in one tuple.


```shell
bash train.sh
```

## Test

Run the test script with `<MODEL PATH>`, e.g. 'logs/saved_models/pitts30k-vgg16/conv5-sare_ind-lr0.001-tuple1/model_best.pth.tar'

```shell
bash test.sh <MODEL PATH>
```