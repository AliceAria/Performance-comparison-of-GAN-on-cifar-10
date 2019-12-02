# Performance-comparison-of-GAN-on-cifar-10
Performance comparison of ACGAN, BEGAN, CGAN, DRAGAN, EBGAN, GAN, infoGAN, LSGAN, VAE, WGAN, WGAN_GP on cifar-10

Reference：https://github.com/hwalsuklee/tensorflow-generative-model-collections <br>
The original code is for data MNIST, we changed the network structure to apply to cifar-10 and test Inception Score. <br>
The net structures are almost same.<br>
The following results can be reproduced with command:
>python main.py --dataset cifar-10 --gan_type <TYPE> --epoch 60 --batch_size 64

#ACGAN <br>
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/ACGAN_IS.png)  

#BEGAN <br>
The result is not well,we don't pay much time to to adjust the superparameters.
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/BEGAN_IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/BEGAN_train_59_0715.png)  

#CGAN <br>
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/CGAN_IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/CGAN_epoch059_test_all_classes.png) 

#DRAGAN <br>
Stable, robust, fast convergent. The best variation of GAN I have ever seen.
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/DRAGAN_epoch099IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/DRAGAN_epoch059_test_all_classes.png) 

#EBGAN <br>
The net structure is the same as BEGAN, but collapse.

#GAN <br>
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/GAN_epoch059IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/GAN_epoch059_test_all_classes.png)

#infoGAN <br>
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/infoGAN_epoch059IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/infoGAN_epoch059_test_all_classes_style_by_style.png)

#LSGAN <br>
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/LSGAN_epoch059IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/LSGAN_epoch059_test_all_classes.png)

#WGAN <br>
Not as well as paper. The net structure is the same as GAN, but converges too slowly.
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/WGAN_epoch059IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/WGAN_epoch059_test_all_classes.png)

#WGAN_GP <br>
The first figure for IS was obtained after 60 epochs. Restore the weights, update another 240epochs and get figure 2. There are total 300 epochs for Discriminator, but only 60 epochs for generator (The same times as other models). Converges slowly.<br>
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/WGAN_GP_epoch059IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/WGAN_GP_epoch299IS.png) 
![](https://github.com/AliceAria/Performance-comparison-of-GAN-on-cifar-10/raw/master/images/WGAN_GP_epoch299_test_all_classes.png)

#VAE <br>
Collapsed. We also try to add or subtract bn layers, but it doesn't work.
