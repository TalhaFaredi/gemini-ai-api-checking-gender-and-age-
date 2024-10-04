# Google Generative AI Project - Text & Image Analysis

This project demonstrates how to use Google Generative AI to perform text generation and image-based content generation. The application generates textual responses to queries like "Most Powerful Anime Characters" and estimates details from images, such as gender and age of a person.

## Features
- Text content generation using the `gemini-pro` model.
- Image content analysis using the `gemini-pro-vision` model.
- Examples include generating philosophical quotes, anime character rankings, and estimating characteristics from images.

## Prerequisites
- Python 3.x
- Google Generative AI API Key (you can generate it from [MakerSuite](https://makersuite.google.com/app/apikey))
- Installed libraries:
  - `google-generativeai`
  - `Pillow` (for image processing)
  - `tqdm` and `ipywidgets` (for handling progress bars)

## Installation

1. Clone the repository or download the project files.
2. Install the required dependencies:

```bash
pip install google-generativeai tqdm ipywidgets pillow
```

3. If you see a `tqdm` warning (`IProgress not found`), make sure to update Jupyter and ipywidgets:

```bash
pip install --upgrade jupyterlab ipywidgets
```

## API Key Setup
You will need to configure your Google Generative AI API key before running the project. You can get your API key from [MakerSuite](https://makersuite.google.com/app/apikey).

In your Python script, configure the API key as follows:

```python
genai.configure(api_key='Your API Key Here')
```

Replace `'Your API Key Here'` with your actual API key.

## Usage

### 1. Text Generation

The `gemini-pro` model is used for text generation. You can use it to generate content based on a given prompt. For example:

```python
response_text = text_model.generate_content("Most Powerful Anime Character of all time")
print(response_text.text)
```

### 2. Image Analysis

The `gemini-pro-vision` model is used for image-based content generation. You can provide an image and ask questions like "What is the gender of the person?" or "What is the age of the person?"

```python
img = Image.open('path_to_image.jpg')
response_gender = vision_model.generate_content(["what is the estimated gender", img])
print(response_gender.text)
```

### Example Code

Here is a quick example to get you started:

```python
import google.generativeai as genai
from PIL import Image

# Set your API key
genai.configure(api_key='Your API Key Here')

# Text model usage
text_model = genai.GenerativeModel('gemini-pro')
response = text_model.generate_content("Most Powerful Anime Character of all time")
print(response.text)

# Image model usage
img = Image.open('path_to_image.jpg')
vision_model = genai.GenerativeModel('gemini-pro-vision')
response_gender = vision_model.generate_content(["what is the estimated gender", img])
print(response_gender.text)
```

## Troubleshooting

- If you encounter an issue with progress bars not showing, run the following command to install or update `ipywidgets`:

```bash
pip install ipywidgets
```

- Ensure your API key is valid and has access to the Google Generative AI services.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Google for providing the Generative AI models.
- OpenAI for inspiration in Generative AI projects.

---

