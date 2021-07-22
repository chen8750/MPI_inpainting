# Image Inpainting Based on Multi-frequency Probabilistic Inference Model
[MM 2020 Paper](https://doi.org/10.1145/3394171.3413891) | 
[Poster](https://github.com/ChenWang8750/MPI-model/blob/main/imgs/MPI_Poster.pdf) |
[BibTex](#citing)
<br>

This is an official python implementation of MPI-model. 

## Example results
<img src="https://github.com/ChenWang8750/MPI-model/blob/main/imgs/sample.pdf" width="1000"/>

## Architecutre
<img src="https://github.com/ChenWang8750/MPI-model/blob/main/imgs/arc.pdf" width="1000"/> 

# Getting started
## Installation
This code was tested with Pytoch 0.4.0, CUDA 9.0, Python 3.6 and Ubuntu 16.04

- Install Pytoch 0.4, torchvision, and other dependencies from [http://pytorch.org](http://pytorch.org)
- Install python libraries [visdom](https://github.com/facebookresearch/visdom) and [dominate](https://github.com/Knio/dominate) for visualization

```
pip install visdom dominate
```
- Clone this repo:

```
git clone https://github.com/ChenWang8750/MPI-model
cd MPI-model
```

## Datasets
- ```face dataset```: 200602 training images and  2000 test images from [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) and 28000 training images and  2000 test images from the high-resolution [CelebAMask-HQ dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)
- ```building dataset```: 14900 training images and 100 test images from [Paris](https://github.com/pathak22/context-encoder)
- ```scene dataset```: original training and val images from [Places2](http://places2.csail.mit.edu/)


## Training
- Train a model:

```
python train.py --name celeba_random --img_file your_image_path
```
- Set ```--mask_type``` in options/base_options.py for different training masks. ```--mask_file``` path is needed for **external irregular mask**, such as the irregular mask dataset provided by [Liu et al.](http://masc.cs.gmu.edu/wiki/partialconv).
- To view training results and loss plots, run ```python -m visdom.server``` and copy the URL [http://localhost:8097](http://localhost:8097).
- Training models will be saved under the **checkpoints** folder.
- The more training options can be found in **options** folder.

## Testing

- Test the model

```
python test.py  --name celeba_random --img_file your_image_path
```
- Set ```--mask_type``` in options/base_options.py to test various masks. ```--mask_file``` path is needed for **3. external irregular mask**,
- The default results will be saved under the *results* folder. Set ```--results_dir``` for a new path to save the result.

## Pretrained Models
Download the pre-trained models using the following links and put them under```checkpoints/``` directory.

- ```center_mask model```: [CelebAMask_HQ] | [Paris]
- ```random_mask model```: [CelebA] |  [Places2]


## Citation

If you use this code, please consider citing:

```
@inproceedings{wang2020image,
  title={Image Inpainting Based on Multi-frequency Probabilistic Inference Model},
  author={Wang, Jin and Wang, Chen and Huang, Qingming and Shi, Yunhui and Cai, Jian-Feng and Zhu, Qing and Yin, Baocai},
  booktitle={ACM MM},
  pages={1--9},
  year={2020}
}
```
## Contacts

Please contact _chenwang8750@gmails.com_  or open an issue for any questions or suggestions.

Thanks! (●'◡'●)

## Acknowledgments
Thanks the author of  [Pluralistic-Inpainting](https://github.com/lyndonzheng/Pluralistic-Inpainting) for their excellent work. 
