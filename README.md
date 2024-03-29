# AiC Dataset

AiC (_Attributes in Crowd_) is a novel synthetic dataset for people attribute recognition in presence of strong occlusions created by exploiting the highly photorealistic video game *Grand Theft Auto V*. 
It features 125,000 samples, all being a unique person, each of which is automatically labeled with information concerning visual attributes, as well as joint locations.

![banner](https://github.com/fabbrimatteo/AiC-Dataset/blob/master/aic_banner.jpg)


## Obtain the Dataset

You can download AiC [here](https://aimagelab.ing.unimore.it/go/AiC). By downloading the dataset you agree on the following statement: "I declare that I will use the AiC Dataset for research and educational purposes only, since I am aware that commercial use is prohibited. I also undertake to purchase a copy of Grand Theft Auto V."

## `AiC-Dataset` Contents

After the data download, your `AiC-Dataset` directory will contain the following files:

- `crops`: directory with image samples. For each sample `x` we have:

    - `x.jpg`: fully visible sample
	- `x_occ.jpg`: occluded sample

- `annotations.json`: annotation file of the whole dataset

- `train.json`: train split containing the ids used as training set

- `test.json`: test split containing the ids used as test set


## Annotations 


The annotation file consists of a list of dictionaries. Each element of the list is a sample of the dataset. Each dictionary is organized as follows:

| Key          | Description                                                 |
| ------------ | ----------------------------------------------------------- |
| `attributes` | list of binary attributes; see 'Attributes' subsection      |
| `pose`       | list of joints; see 'Joins' subsection                      |
| `id`         | unique identifier of the sample                             |


**IMPORTANT**: given the `id`, the correspondent fully visible image is `crops/id.jpg`, while the occluded one is `crops/id_occ.jpg`.


### Attributes

The list of binary attributes is ordered as follows:

```
 0: Female
 1: Age17-30
 2: Age31-45
 3: BodyNormal
 4: BodyThin
 5: BaldHead
 6: LongHair
 7: BlackHair
 8: Hat
 9: Muffler
10: Shirt
11: Sweater
12: Jacket
13: TightHood
14: ShortSleeve
15: LongTrousers
16: Skirt
17: Jeans
18: Tights
19: shoes-Leather
20: shoes-Sport
21: shoes-Boots
22: Backpack
23: Eyeglasses
```

### Joins

Each joint is a list containing:

| Element index     | Name          | Description                                                         |
| ----------------- | ------------- | ------------------------------------------------------------------- |
| 0                 | joint type    | identifier of the type of joint; see 'Joint Types' subsection       |
| 1                 | x2D           | 2D _x_ coordinate of the joint in pixel                             |
| 2                 | y2D           | 2D _y_ coordinate of the joint in pixel                             |
| 3                 | occluded      | `1` if the joint is occluded; `0` otherwise                         |
| 4                 | self-occluded | `1` if the joint is occluded by its owner; `0` otherwise            |

The association between numerical identifier and type of joint is the following:

```
 0: head_top
 1: head_center
 2: neck
 3: right_clavicle
 4: right_shoulder
 5: right_elbow
 6: right_wrist
 7: left_clavicle
 8: left_shoulder
 9: left_elbow
10: left_wrist
11: spine0
12: spine1
13: spine2
14: spine3
15: spine4
16: right_hip
17: right_knee
18: right_ankle
19: left_hip
20: left_knee
21: left_ankle
```


## Citation

This dataset was introduced in the paper ["Can Adversarial Networks Hallucinate Occluded People With a Plausible Aspect?"](https://arxiv.org/abs/1901.08097).
We believe in open research and we are happy if you find this data useful.   
If you use it, please cite our works.

```latex
@article{fulgeri2019can,
  title     = {Can Adversarial Networks Hallucinate Occluded People With a Plausible Aspect?},
  author    = {Fulgeri, Federico and Fabbri, Matteo and Alletto, Stefano and Calderara, Simone and Cucchiara, Rita},
  journal   = {arXiv preprint arXiv:1901.08097},
  year      = {2019}
}
```

```latex
@inproceedings{fabbri2018learning,
  title     = {Learning to Detect and Track Visible and Occluded Body Joints in a Virtual World},
  author    = {Fabbri, Matteo and Lanzi, Fabio and Calderara, Simone and Palazzi, Andrea and Vezzani, Roberto and Cucchiara, Rita},
  booktitle = {European Conference on Computer Vision (ECCV)},
  year      = {2018}
}
```
