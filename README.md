# Image colorization using GANs
The code adds color to single channeled images (similar to Black and White images) using GANs 

This code is a project which is used for converting a Black and white image (single channeled) into a colored one. Currently, the architecture uses CIFAR10 dataset for training. The model can be easily trained using free online GPUs like Google colab.

To run the above code:
1.  Make account on Google colab.
2.  Make folder on drive for storing and retriving trained models (in my case, I have made a folder 'newGAN' which stores the model)
3.  Run the all the code cells.
4.  Allow access to the use google drive if asked.
5.  If you are training the model for first time, the reuse variable in the 3rd last cell should be set to False. On training         otherwise, set it to true for reusing the trained model.
6.  If in case the GAN starts to have mode collapse, uncomment two lines in the last cell as stated by a comment.
7.  For getting email notification on completing the specified number of epochs, add your email and password in the last portion of           last cell.


The model requires approximately 35 hrs to train. Use Google Colab or similar GPU for training purpose.

Note: The sample images in PDF file has Greenish Blue color instead of Black and white color as input. This color was used because it gave us better visualization of colorless image structure during training, but the model works fine for Black and White images too.

The architecture of the network is inspired from the paper 'Image Colorization using Generative Adversarial Networks' by Kamyar Nazeri, Eric Ng, and Mehran Ebrahimi. (https://arxiv.org/abs/1803.05400)

For viewing the result of the model, add this code at the end of the training session and run the cell.

plt_indices = np.random.randint(50000,size=3)                                                                                              
plt_a = x[plt_indices]                                                                                                                  
plt_b = gen.predict(plt_a)                                                                                                                                   
plt_c = y[plt_indices]                                                                                                                             
fig = plot(plt_a,plt_b,plt_c,3)                                                                                                                                          
plt.show()                                                                                                                                     
plt.close(fig)                                                                                                                         
print(np.min(plt_b-plt_c/255))                           








