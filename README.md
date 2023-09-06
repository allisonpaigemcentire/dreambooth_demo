# dreambooth_demo
Train your own model

First, confirm you have at least 5GB of space free in your Google Drive, and prepare your image dataset (or use the C-3PO dataset in this repo). Your dataset should include at least 20 images of the subject in different backgrounds, profiles, etc and each image should be cropped to 512 x 512 (the ratio the model expects). I suggest using [ImageMajick](https://imagemagick.org/script/mogrify.php) to batch crop from the command line. You can also get image datasets from [Kaggle](https://www.kaggle.com/datasets?search=image)

Next, navigate to the Colab NoteBook: [Colab Notebook](https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb)

Click "Play" to:

1. Check type of GPU and VRAM available. Click "run anyway" in the dialogue box that appears.


2. Install Requirements


3. Login to HuggingFace 🤗

[Create a HuggingFace Account](https://huggingface.co/join)

Navigate to [Settings/tokens](https://huggingface.co/settings/tokens) and create a user access token with WRITE access, then copy and paste the token into the colab notebook.
*Note: The notebook instructs you to read the license and tick the checkbox if you agree. I have not encountered a checkbox with any license; you may only need to read the license for the model you choose.


4. Settings and run (easy mode):

   <img width="696" alt="Screenshot 2023-09-04 at 1 14 48 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/099cb8e5-1e63-468c-8af3-6e7d6fd84927">

   Click "Connect to Google Drive" in the dialogue box that appears.


5. Start Training:
   Edit the concepts list. Choose a unique identifier for the instance prompt, e.g. "robotMaria" and a generic identifier for the class prompt ("robot)". The unique identifier you choose will be the prompt you use on your final model.
   
   <img width="806" alt="Screenshot 2023-09-04 at 11 31 44 AM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/5913d75d-a42a-4600-a790-fffd0d17071b">


6. Upload your image dataset (easy mode):
  Expand the Files menu on the lefthand side of the notebook and upload your files to the data/<instance prompt> folder created in the previous step. Once the upload completes, click play to finalize this step.


7. Edit the python command:

   Seed = changing this number will give you slightly different results if you're unhappy with the output of the model after training

   Max train steps (iterations the model makes on each images in training) = play with this setting, but I get good results by using the number of images uploaded x 100

   Save interval = it works well to use the same formula as max train steps

   Sample prompt = the string used for "instance prompt" in step 6

   Click play, then wait 20-30 minutes for training to complete. Keep your browser active to avoid complications/timing out.

    <img width="584" alt="Screenshot 2023-09-04 at 12 01 41 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/66fc3bdd-72a1-4246-83f7-bfcbaa9d6949">


8. Specify the weights directory to use (leave blank for latest)


9. Run to generate a grid of preview images from the last saved weights.
   
   <img width="1408" alt="Screenshot 2023-09-04 at 1 36 33 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/b8e825c2-38b3-4d4b-9118-a1cf43c23fe3">


10. (Optional) Convert weights to .ckpt to use in web UIs like AUTOMATIC1111
    This step creates a .ckpt file (similar to .zip) for you model and saves it to your Google Drive


11. (Optional) Inference: sets up the environment to run and test your model in the notebook


12. (Optional) Run for generating images.
    prompt = the string used for "instance prompt" in step 6, + additional desired details
    negative_prompt = objects to exclude ("hands" is a popular negative prompt)
    num_samples = the number of sample images to generate
    guidance_scale = how closely the model should adhere to the prompt (higher number = more creativity)
    num_inference_steps = for best results, choose a number between 20 and 65
    height = height of output image
    width = width of output image

    <img width="614" alt="Screenshot 2023-09-04 at 1 45 14 PM" src="https://github.com/allisonpaigemcentire/dreambooth_demo/assets/79477856/7c67c2ad-a1a3-4b30-9100-e3b9fe55cd70">


     


