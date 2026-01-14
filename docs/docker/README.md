# Docker Setup & Application Container

## Purpose
Docker is used to containerize the application and ELK components for easy deployment.

---

## Application Code (Log Generator)

**File:** `app/app.py`

```python
from flask import Flask
import logging
import random

app = Flask(__name__)
logging.basicConfig(level=logging.INFO)

@app.route("/")
def home():
    if random.randint(1, 10) > 7:
        logging.error("Random error occurred")
        return "Error logged", 500
    logging.info("Request successful")
    return "Hello from centralized logging app"

app.run(host="0.0.0.0", port=5000)
