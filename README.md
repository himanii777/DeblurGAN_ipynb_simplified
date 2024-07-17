![image](https://github.com/user-attachments/assets/32a92023-6fb6-43a1-a99d-adfe700d47f6)
![image](https://github.com/user-attachments/assets/45a0a45c-0be4-4ccf-9569-b1a81a76b0d5)

I have simplified the deblurgan implementation into a ipynb.
There you can upload your custom dataset, train, test and continue training the pretrained model.

I had encountered a lot of issues while training and some of the tips I can give are:

1. Instead of using nn.BatchNorm2d, try using nn.InstanceNorm2d because of the smaller batch size
2. Start training with same learning rates of disc & generator (0.0001 standard according to the paper)
3. If the generator doesn't seem to improve then change the lr to 0.0002/ train the generator twice per epoch or add noise to both blurred and sharp data
4. When you are using custom dataset, resize it with correct dimensions so that image doesn't distort. I have put AR code inside.
5. Overfitting isn't really an issue for this model however, balancing generator and discriminator can become challenging for which play with their learning rates and training frequnecy.

Loss visualization:

![image](https://github.com/user-attachments/assets/80091dc5-efa5-4ce0-9383-368a4989658e)
![image](https://github.com/user-attachments/assets/c09b9e00-040b-4d70-bdf0-eb28c25491c9)


Original Paper: 
https://arxiv.org/abs/1711.07064

Codes Borrowed from:
https://github.com/KupynOrest/DeblurGAN
https://github.com/The-GAN-g/DeblurGAN

