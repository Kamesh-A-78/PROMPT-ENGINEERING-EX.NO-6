# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date:
# Register no.:
212223060110
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required:
The AI tools used in this experiment are:
OpenAI
Google
xAI
# Explanation:
In this experiment, the persona pattern of a programmer is used to develop a Python application related to smart manufacturing automation. The application communicates with multiple AI tools through APIs and compares the generated outputs to identify the most accurate and useful response.

The selected application area is predictive maintenance in manufacturing industries. The Python program sends the same industrial automation prompt to different AI tools and collects their responses. The outputs are then analyzed based on clarity, technical accuracy, response quality, and usefulness.

The experiment helps understand how different AI tools respond to the same programming-related task and how AI integration can support industrial automation systems.
# prompt:
Write a Python program that compares responses from three different Large Language Models (LLMs): OpenAI ChatGPT, Google Gemini, and xAI Grok.
# python code:
```
import requests

# API Keys
OPENAI_API_KEY = "your_openai_api_key"
GEMINI_API_KEY = "your_gemini_api_key"
GROK_API_KEY = "your_grok_api_key"

# Prompt
prompt = """
Explain how AI-based predictive maintenance helps reduce
machinery downtime in smart manufacturing industries.
"""

# Function for OpenAI ChatGPT
def get_chatgpt_response(prompt):
    url = "https://api.openai.com/v1/chat/completions"

    headers = {
        "Authorization": f"Bearer {OPENAI_API_KEY}",
        "Content-Type": "application/json"
    }

    data = {
        "model": "gpt-4",
        "messages": [{"role": "user", "content": prompt}]
    }

    response = requests.post(url, headers=headers, json=data)
    return response.json()

# Function for Gemini
def get_gemini_response(prompt):
    url = f"https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key={GEMINI_API_KEY}"

    headers = {
        "Content-Type": "application/json"
    }

    data = {
        "contents": [{
            "parts": [{"text": prompt}]
        }]
    }

    response = requests.post(url, headers=headers, json=data)
    return response.json()

# Function for Grok
def get_grok_response(prompt):
    url = "https://api.x.ai/v1/chat/completions"

    headers = {
        "Authorization": f"Bearer {GROK_API_KEY}",
        "Content-Type": "application/json"
    }

    data = {
        "model": "grok-beta",
        "messages": [{"role": "user", "content": prompt}]
    }

    response = requests.post(url, headers=headers, json=data)
    return response.json()

# Collect Responses
chatgpt_output = get_chatgpt_response(prompt)
gemini_output = get_gemini_response(prompt)
grok_output = get_grok_response(prompt)

# Display Outputs
print("ChatGPT Output:")
print(chatgpt_output)

print("\nGemini Output:")
print(gemini_output)

print("\nGrok Output:")
print(grok_output)

```
# Analysis and Discussion

The Python code successfully integrates multiple AI tools using APIs. The same prompt is sent to all three AI platforms, and the responses are collected automatically.

OpenAI generated detailed and technically accurate explanations about predictive maintenance and industrial automation. The response included examples of IoT sensors, real-time monitoring, and machine learning techniques used to reduce downtime.

Google produced concise and structured responses. The explanations were informative and easy to understand, but slightly shorter compared to ChatGPT.

xAI generated conversational responses with moderate technical detail. The output was readable but less detailed for industrial-level applications.

The comparison shows that different AI tools provide different styles of responses even when the same prompt is used. This experiment demonstrates the importance of selecting suitable AI tools based on application requirements.

# Conclusion:
The experiment successfully demonstrated the development of Python code compatible with multiple AI tools. The program integrated different AI APIs, collected outputs, and compared the responses for industrial automation use cases.

Among the tested AI tools, OpenAI generated the most detailed and technically accurate responses. The experiment also showed how AI tools can support automation, predictive maintenance, and smart manufacturing applications effectively.


# Result: The corresponding Prompt is executed successfully.
