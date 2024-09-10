# KAN-CUT
# Kolmogorov-Arnold Networks in Contrastive Unpaired Translation (KAN-CUT)

### [paper](https://arxiv.org/pdf/2408.08216)


### Getting started

- Clone this repo:
```bash
git clone https://github.com/amaha7984/KAN-CUT
cd KAN-CUT
```

### KAN-CUT Training and Test
- Download the horse2zebra dataset from CycleGAN github page: https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix/blob/master/datasets/download_cyclegan_dataset.sh

The dataset downloaded should be placed in the `./datasets/horse2zebra/`.

- Train the KAN-CUT model:
```bash
python train.py --dataroot ./datasets/horse2zebra --name horse2zebra_KANCUT --CUT_mode kancut
```
The checkpoints will be stored at `./checkpoints/ horse2zebra_KANCUT/web`.

- Test the trained KAN-CUT model:
```bash
python test.py --dataroot ./datasets/ horse2zebra --name horse2zebra_KANCUT --CUT_mode kancut
```
The test results will be saved to an HTML file located at: `./results/horse2zebra_KANCUT/latest_train/index.html`.


### KAN-CUT
KAN-CUT is trained with identity preservation loss and with `lambda_NCE=1`, closely aligning with the CUT approach

### [Datasets]

1.	The Horse2Zebra dataset can be downloaded from CycleGAN repository. Please visit this link https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix
2.	The Cat2Dog dataset is a subset of the AFHQ dataset. Please visit https://github.com/clovaai/stargan-v2 and download the AFHQ dataset.

### Citation
If you use this code for your research, please cite our [paper](https://arxiv.org/pdf/2408.08216).


### Acknowledgments
Our code is developed based on [CUT](https://github.com/taesungp/contrastive-unpaired-translation) and [efficient-kan](https://github.com/Blealtan/efficient-kan). We appreciate the great work provided by CUT. We thank [pytorch-fid](https://github.com/mseitzer/pytorch-fid) for facilitating the computation of FID scores. 
