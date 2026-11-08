# 03 — APIs and Model Providers

An API is a defined way for programs to communicate.

    your app → HTTPS request → model provider
    your app ← HTTPS response ← model provider

## JSON
JSON represents structured information:

    {
      "message": "Explain neural networks",
      "temperature": 0.2
    }

Actual fields depend on the provider's official API documentation.

## API keys
An API key authorizes use of a service.
- Store it in an environment variable or secret manager.
- Never put it in frontend/browser code.
- Never commit it to GitHub.
- If exposed, revoke it and replace it.
- Use spending limits where available.

Python can read a key from the environment:

    import os
    api_key = os.getenv("MODEL_API_KEY")

Never print the secret.

## Errors
Handle invalid credentials, rate limits, timeouts, network failures, invalid requests, and provider outages. Use bounded retries and clear messages; never retry forever.

## Provider independence
Keep provider-specific code in one module. The rest of your app can call a generic function such as generate_text(prompt).

## Exercise
Draw the request/response flow and list three errors your app should handle.