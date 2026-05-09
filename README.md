import requests

def ask_human(image_url, question):
    response = requests.post(
        "https://human-api-gamma.vercel.app/api/verify",
        json={
            "api_key": "sk_human_...",
            "image_url": image_url,
            "question": question,
            "webhook_url": "https://your-server.com/webhook"
        }
    )
    return response.json()

# Example: AI gets confused by a captcha
ask_human("https://example.com/captcha.jpg", "Are there traffic lights here?")
