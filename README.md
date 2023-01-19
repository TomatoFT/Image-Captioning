# Image Captioning with EfficentNet and Transformer
<h3>Tech stack and Tools</h3> 
<li>Tensorflow</li>
<li>Streamlit</li>
<li>PostgresQL</li>
<li>Visual Studio Code</li>
<li>Anaconda</li>
<li>Google Colab (Jupiter Notebook)</li>

## What is Image Captioning problem ?
<p>Image captioning is the process of generating a natural language description of an image. It is a task in the field of computer vision and natural language processing. The goal of image captioning is to generate a coherent and fluent sentence that accurately describes the image content.</p>

An image captioning system typically consists of two main components:

<li>An image feature extractor: This component is responsible for extracting features from the input image, such as object locations, sizes, and colors.
A natural language generator: This component takes the image features as input and generates a natural language description of the image. The image feature extractor can be a pre-trained convolutional neural network (CNN) such as ResNet, Inception, or VGG. These networks are trained on large image datasets, such as ImageNet, to recognize various objects and scenes in images.

<li>The natural language generator can be a Recurrent Neural Network (RNN) or a transformer network such as GPT-2 or BERT that is trained to generate text based on the input image features.</li>

<li>The generated captions are typically evaluated using metrics such as BLEU, METEOR, ROUGE, and CIDEr.</li>

## How to run this project

This project uses streamlit to demo the result of EfficentNet + Transformer (Trained with 11 epoches) and connect with PostgreSQL to save the information about the picture and some metadata to a database.

So first you will need to install Anaconda, PostgreSQL and Python 3. Depend on your OS, there maybe many different ways to install it. In this project I use Ubuntu OS to install all of them. So I will put some video tutorial to install them here.

PostgreSQL + pgAdminIII: https://www.youtube.com/watch?v=-LwI4HMR_Eg

Python 3: https://www.youtube.com/watch?v=z3Hdewxuuoo

Anaconda: https://www.youtube.com/watch?v=5kuqIFDouXY

After completed install these things, you can do the below step.
### Clone the project

```
git clone https://github.com/TomatoFT/Image-Captioning-with-Transformer
cd Image-Captioning-with-Transformer
```
### Create and Enter the Anaconda Environment

```
conda create --name image-captioning
conda activate image-captioning
```
### Install dependencies
```
conda install -c anaconda pip
pip install -r requirements.txt
```

### Connect Streamlit to PostgreSQL
Read this document from Streamlit: https://docs.streamlit.io/knowledge-base/tutorials/databases/postgresql#add-username-and-password-to-your-local-app-secrets. Then go to pgAminIII, press _Add the connection to server_ and fill this form.


![image](https://user-images.githubusercontent.com/79329526/213474760-fb74bf0c-52b5-4f75-a098-9cfceb068756.png)

In .streamlit/secrets.toml file. Change these information to YOUR PostgreSQL information. 

```
[postgres]
host="localhost"
port=5432
user="postgres"
password="12345"
database="postgres"
```
### Open the streamlit file and run demo

```
streamlit run web.py
```

Here is the demo: 
<video width="320" height="240" controls>
  <source src="model/demo_image_captioning.webm" type="video/mp4>
</video>
