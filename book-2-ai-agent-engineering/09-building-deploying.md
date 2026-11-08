# 09 — Building and Deploying an Agent

## Separate components
A project may use this layout:

    agent-project/
      app.py
      model_client.py
      tools.py
      prompts.py
      memory.py
      tests/
      README.md
      .env.example
      .gitignore

## Build locally first
1. Command-line interface.
2. One model call.
3. One safe tool.
4. Input validation.
5. Tests.
6. Logging.
7. UI only after the core works.

## Secrets
Use environment variables. Example placeholder file:

    MODEL_API_KEY=replace_me

Never upload your real .env file.

## Deployment checklist
- Remove secrets from code and logs.
- Add authentication if needed.
- Limit requests and costs.
- Validate input.
- Check permissions.
- Add error handling.
- Test with fake data.
- Explain stored data.
- Provide stop/reset controls.

A prototype is not automatically production-ready. Test security, privacy, reliability, and failure behavior before real users depend on it.

## Exercise
Write a README explaining your agent, setup, safe configuration, and limitations.