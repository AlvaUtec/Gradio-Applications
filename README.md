# Gradio Applications

## Description

This projects uses the open-source library Gradio. Gradio is a Python library that allows you to create a UI for your model in a few lines of code. It is a great tool for quickly prototyping and sharing your models with others. In this project, we will explore different examples of Gradio UIs for different types of models, including image captioning, text generation, and chatbot. For more information on Gradio, you can check out the official documentation [here](https://gradio.app/).

This aims to give an overview of how to use this library in different scenarios, and how to integrate it with Hugging Face models. The Hugging Face models are hosted on the Hugging Face Hub, which is a repository of pre-trained models that can be easily accessed and used in your projects. For more information on the Hugging Face Hub, you can check out the official documentation [here](https://huggingface.co/).

## Table of Contents

- [Gradio Applications](#gradio-applications)
  - [Description](#description)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
  - [How to get your own Hugging Face API key (token)](#how-to-get-your-own-hugging-face-api-key-token)
      - [Save your user access tokens to environment variables](#save-your-user-access-tokens-to-environment-variables)
  - [Files](#files)
    - [Summarization and entity recognition](#summarization-and-entity-recognition)
    - [Image captioning](#image-captioning)
    - [Image generation](#image-generation)
    - [Generation and description](#generation-and-description)
    - [Chatbot](#chatbot)
  - [Acknowledgements](#acknowledgements)

## Installation

For this repository, we will need to install different libraries, so you can run the `requirements.txt` file to install all the necessary libraries.

```bash
pip install -r requirements.txt
```

## How to get your own Hugging Face API key (token)

Hugging Face "API keys" are called "User Access tokens".  

You can create your own User Access Tokens here: [Access Tokens](https://huggingface.co/settings/tokens).

#### Save your user access tokens to environment variables
To save your access token securely on your own machine:
- Create a `.env` file in the root directory of your project.
- Edit the file to contain the following:  
`HF_API_KEY="abc123"` replace that string with your user access token.
- Save the .env file.
- Install Python-dotenv, which allows you to run that first code cell at the top of this jupyter notebook:  
`pip install python-dotenv`


For more information on how to get your own access tokens, please see [User access tokens](https://huggingface.co/docs/hub/security-tokens#:~:text=To%20create%20an%20access%20token,you're%20ready%20to%20go!)

## Files

### Summarization and entity recognition

In the first file called `E1_Text_summarization.ipynb`, we use a two models, [`sshleifer/distilbart-cnn-12-6`](https://huggingface.co/sshleifer/distilbart-cnn-12-6) for test summarization and [`dslim/bert-base-NER`](https://huggingface.co/dslim/bert-base-NER) for entity recognition. The objects of Gradio used here are `gr.Interface`, `gr.Textbox` and `gr.HighlightText`.

### Image captioning

In the second file called `E2_Image_captioning_app.ipynb`, we use the model [`Salesforce/blip-image-captioning-base`](https://huggingface.co/Salesforce/blip-image-captioning-base) for image captioning. The objects of Gradio used here are `gr.Interface`, `gr.Image` and `gr.Textbox`.

### Image generation

In the third file called `E3_Image_generation_app.ipynb`, we use the model [`runwayml/stable-diffusion-v1-5`](https://huggingface.co/runwayml/stable-diffusion-v1-5) for image generation. Here we use the previous elements and add `gr.Slider` to control the temperature of the model, and `gr.Button` to generate the image, `gr.Block` to group the elements, `gr.Row` and `gr.Column` to organize the elements.

### Generation and description

In the fourth file called `E4_Describe_and_generate_app.ipynb`, we use the same models as before but integrating them into a single interface to show a more complex example.

### Chatbot
In the fifth file called `E5_Chatbot_app.ipynb`, we use the model [`falcon-7b-instruct`](https://huggingface.co/tiiuae/falcon-7b-instruct) for the LLM. So we use `gr.Chatbot` for the interface, integrated as well with the other elements used before.

## Acknowledgements

- [Gradio Repository](https://github.com/gradio-app/gradio)
- [Hugging Face](https://huggingface.co/)