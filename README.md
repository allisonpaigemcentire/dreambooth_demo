# dreambooth_demo
Train your own model

First, confirm you have at least 5GB of space free in your Google Drive, and prepare your image dataset (or use the C-3PO dataset in this repo). Your dataset should include at least 20 images of the subject in different backgrounds, profiles, etc and each image should be cropped to 512 x 512 (the ratio the model expects). I suggest using [ImageMajick](https://imagemagick.org/script/mogrify.php) to batch crop from the command line. You can also get image datasets from [Kaggle](https://www.kaggle.com/datasets?search=image)

Next, navigate to the Colab NoteBook: [Collab Notebook](https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb)

Click "Play" to:

1. Check type of GPU and VRAM available. Click "run anyway" in the dialogue box that appears.

2. Install Requirements:
   <img width="1112" alt="Screenshot 2023-09-04 at 11 20 22 AM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/c014b2d3-0aeb-4646-8660-59ea59149153">


4. Login to HuggingFace 🤗
[Create a HuggingFace Account](https://huggingface.co/join)
Navigate to [Settings/tokens](https://huggingface.co/settings/tokens) and create a user access token with write access, then copy and paste the token into the colab notebook.
*Note: The notebook instructs you to read the license and tick the checkbox if you agree. I have not encountered a checkbox with any license; you may only need to read the license for the model you choose.

5. Settings and run (easy mode):

   <img width="714" alt="Screenshot 2023-09-04 at 12 06 25 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/4df40727-15a9-4661-b406-bc649c007410">
   
   Click "Connect to Google Drive" in the dialogue box that appears.

7. Start Training:
   Edit the concepts list. Choose a unique identifier for the instance prompt, e.g. "robotMaria" and a generic identifier for the class promt ("robot)". The unique identifier you choose will be the prompt you use on your final model.
   <img width="806" alt="Screenshot 2023-09-04 at 11 31 44 AM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/ed3d511f-5402-4cc5-9638-f869ce1d5034">

8. Upload your image dataset (easy mode):
  Expand the Files menu on the lefthand side of the notebook and updload your files to the data/<instance prompt> folder created in the previous step. Once the upload completes, click play to finalize this step.

9. Edit the python command:
   Seed = changing this number will give you slightly different results if you're unhappy with the output of the model after training
   Max train steps (iterations the model makes on each images in training) = the number of images you uploaded x 100
   Save interval = the number of images you uploaded x 100
   Sample prompt = the string used for "instance prompt" in step 6.
   Click play, then wait 20-30 minutes for training to complete. Keep your browser active to avoid complications/timing out.
   <img width="584" alt="Screenshot 2023-09-04 at 12 01 41 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/3950fdc4-c5a0-4e7c-9476-0a714b24bfdd">

10. Specify the weights directory to use (leave blank for latest)

11. Run to generate a grid of preview images from the last saved weights.
    <img width="1404" alt="Screenshot 2023-09-04 at 12 34 17 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/3f1f7312-7bb8-45dc-8176-1bf9d0301743">

12. (Optional) Convert weights to .ckpt to use in web UIs like AUTOMATIC1111
    This step creates a .ckpt file (similar to .zip) for you model and saves it to your Google Drive

13. (Optional) Inference: sets up the environment to run and test your model in the notebook

14. (Optional) Run for generating images.
    prompt = the string used for "instance prompt" in step 6, + additional desired details
    negative_prompt = objects to exclude ("hands" is a popular negative prompt)
    num_samples = the number of sample images to generate
    guidance_scale = how closely the model should adhere to the prompt (higher number = more creativity)
    num_inference_steps = for best results, choose a number between 20 and 65
    height = height of output image
    width = width of output image

    <img width="664" alt="Screenshot 2023-09-04 at 12 52 11 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/006fa021-ce28-4406-9fa3-00643a4f35d6">

     


