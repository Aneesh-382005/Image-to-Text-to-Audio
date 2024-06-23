# Image-to-Text-to-Audio

This notebook demonstrates how to extract text from an image and convert it into an audio file using Tesseract OCR and Google Text-to-Speech (gTTS). The notebook includes the following steps:

### 1. Install Dependencies
```
!sudo apt install tesseract-ocr &> /dev/null
!pip install pytesseract gTTS Pillow==9.0.0 &> /dev/null
```
### 2. Import the libraries
```
import pytesseract # For OCR (Optical Character Recognition)
from PIL import Image # For handling image files
import gtts # For converting text to speech
from IPython.display import Audio, display # For playing audio in colab 
```
### 3. Load Image
```
img = Image.open('/content/Image.png')
print(img)
```

### 4. Extract Text from Image
```
result = pytesseract.image_to_string(img)
print(result)
```
### 5. Convert Extracted Text to Speech
```
tts = gtts.gTTS(result)
tts.save('Audio.mp3')
```
### 6. Display the Audio file
```
display(Audio('Audio.mp3'))
```
