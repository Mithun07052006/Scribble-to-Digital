#Scribble to Digital

Scribble to Digital is an AI-powered system that converts rough hand-drawn sketches or handwritten notes into clean digital content. Using computer vision and AI models, the system detects shapes, text, and structures from an image and transforms them into organized digital formats such as editable text, diagrams, or structured data. ✏️➡️💻🤖

Quick Start (Local)

Install dependencies

pip install fastapi uvicorn pillow opencv-python requests

Run the application

python app.py

Send an image

curl -X POST http://localhost:8000/convert \
-F "file=@scribble.jpg"
Using a Real AI Provider

Example using OpenAI Vision model

from openai import OpenAI

client = OpenAI()

response = client.responses.create(
    model="gpt-4.1",
    input=[{
        "role": "user",
        "content": [
            {"type": "input_text", "text": "Convert this sketch into structured data"},
            {
                "type": "input_image",
                "image_url": "https://example.com/scribble.png"
            }
        ]
    }]
)

print(response.output_text)
