## Feeding the zombies: Synthesizing brain volumes using a 3D progressive growing GAN<br>

Anders Eklund, Link?ping University

![Representative image](https://raw.githubusercontent.com/wanderine/ProgressiveGAN3D/master/brain.png)<br>
A brain that was dreamed up by a random number generator.

**Abstract:**<br>
*Deep learning requires large datasets for training (convolutional) networks with millions of parameters. In neuroimaging, there are few open datasets with more than 100 subjects, which makes it difficult to, for example, train a classifier to discriminate controls from diseased persons. Generative adversarial networks (GANs) can be used to synthesize data, but virtually all research is focused on 2D images. In medical imaging, and especially in neuroimaging, most datasets are 3D or 4D. Here we therefore present preliminary results showing that a 3D progressive growing GAN can be used to synthesize MR brain volumes.*

## Resources

* [Paper (arXiv)](http://arxiv.org/abs/1912.05357)

All the material, including source code, is made freely available for non-commercial use under the Creative Commons [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/legalcode) license. Feel free to use any of the material in your own work, as long as you give us appropriate credit by mentioning the title and author list of our paper.

This 3D version is based on the original 2D version presented here

* [Paper (arXiv)](https://arxiv.org/abs/1710.10196)

* [Github](https://github.com/tkarras/progressive_growing_of_gans)

## System requirements

* Linux with Anaconda, use environment.yml for setting up the conda environment.
* One or more high-end NVIDIA Pascal or Volta GPUs with 16GB of DRAM. We recommend NVIDIA DGX station or better (4 Tesla V100 GPUs).
* NVIDIA driver 418.87 or newer, CUDA toolkit 10.1 or newer

## Preparing datasets for training

Use the `create_from_nifti` option in dataset_tool.py, which was added to the original 2D implementation.

```
usage: dataset_tool.py [-h] <command> ...

    display             Display images in dataset.
    extract             Extract images from dataset.
    compare             Compare two datasets.
    create_mnist        Create dataset for MNIST.
    create_mnistrgb     Create dataset for MNIST-RGB.
    create_cifar10      Create dataset for CIFAR-10.
    create_cifar100     Create dataset for CIFAR-100.
    create_svhn         Create dataset for SVHN.
    create_lsun         Create dataset for single LSUN category.
    create_celeba       Create dataset for CelebA.
    create_celebahq     Create dataset for CelebA-HQ.
    create_from_images  Create dataset from a directory full of images.
    create_from_hdf5    Create dataset from legacy HDF5 archive.
    create_from_nifti   Create dataset from nifti files

Type "dataset_tool.py <command> -h" for more information.
```


## Training networks

Once the necessary datasets are set up, you can proceed to train your own networks. The general procedure is as follows:

1. Edit `config.py` to specify the dataset and training configuration by uncommenting/editing specific lines.
2. Run the training script with `python train.py`.
3. The results are written into a newly created subdirectory under `config.result_dir`
4. Wait several days (or weeks) for the training to converge, and analyze the results.


