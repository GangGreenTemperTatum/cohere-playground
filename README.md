# [Co:here](https://cohere.ai)

## **Authentication Tips:**

* Via the Python SDK, which contacts the Cohere API you can authenticate numerous ways:
    > **Note**, ensure `.env` is added to `.gitignore` and not added to source control which can expose secrets and keys

1)
- Create an `.env` file in the virtual project with line `export CO_KEY="YOUR_API_KEY_HERE"` and import the `os` module
- Reference the environment variable directly
    - Python code to look like this:

```
import os
import cohere

api_key = os.environ["CO_KEY"]
co = cohere.Client(api_key)
```

----------------------------------------

2)
- Create an `.env` file in the virtual project with line `export CO_KEY="YOUR_API_KEY_HERE"` and import the `os` module
- Call the `os.environ` as a variable = `co_client`
    - Python code to look like this:

```
import os
import cohere

co_client = cohere.Client(f'{os.environ["CO_KEY"]}')
CHUNK_SIZE = 1024
OUTPUT_BASE_DIR = "./"
```

----------------------------------------

3)
- Create an `.env` file in the virtual project with line `export CO_KEY="YOUR_API_KEY_HERE"` and import the `os` module
- Define a variable `api_key` on a new line and reference it using `os.environ`
- Use a class definition to reference this within the code 
    - Python code to look like this:

```
# Cohere API key:
api_key = os.environ["CO_KEY"]
# Set up Cohere client:
co = cohere.Client(api_key)

# Providing API Key Credentials
class CoHere:
    def __init__(self, api_key):
        api_key = config('API_KEY')
        self.co = cohere.Client(api_key)
```
