Designing an application to handle various GitHub webhook events can involve several components. Since you're using Quart, a Python ASGI web microframework, you can make use of its asynchronous capabilities. Below is an example outline of how to structure your application to handle various GitHub webhook events:

### Directory Structure

```
your_project/
├── app/
│   ├── __init__.py
│   ├── routes.py
│   ├── handlers/
│   │   ├── __init__.py
│   │   ├── push_handler.py
│   │   ├── pull_request_handler.py
│   │   └── issues_handler.py
│   └── utils/
│       └── __init__.py
│       └── webhook_validator.py
├── config/
│   └── settings.py
├── main.py
└── requirements.txt
```

### Explanation

- **app/**: Contains all application logic.
  - **routes.py**: Where you define the Quart routes.
  - **handlers/**: Each file here contains classes/functions to handle specific GitHub events like Push, Pull Request, etc.
  - **utils/**: Contains utility functions like webhook validators, common HTTP request functions, etc.

- **config/**: Contains configuration settings like secret tokens, etc.
- **main.py**: Entry point to your Quart application.

### Code Snippets

#### main.py

```python
from quart import Quart
from app.routes import configure_routes

app = Quart(__name__)
configure_routes(app)

if __name__ == "__main__":
    app.run()
```

#### app/__init__.py

```python
# You can initialize your application setup here if needed
```

#### app/routes.py

```python
from quart import Blueprint, request, jsonify
from .handlers import push_handler, pull_request_handler, issues_handler
from .utils.webhook_validator import validate_webhook

webhook_bp = Blueprint('webhook', __name__)

@webhook_bp.route('/webhook', methods=['POST'])
@validate_webhook
async def webhook():
    event_type = request.headers.get('X-GitHub-Event')
    
    if event_type == 'push':
        return await push_handler.handle(request)
    elif event_type == 'pull_request':
        return await pull_request_handler.handle(request)
    elif event_type == 'issues':
        return await issues_handler.handle(request)
    else:
        return jsonify({'msg': 'Event not supported'}), 400

def configure_routes(app):
    app.register_blueprint(webhook_bp)
```

#### app/utils/webhook_validator.py

```python
from quart import request, jsonify, current_app
from functools import wraps

def validate_webhook(f):
    @wraps(f)
    async def decorated_function(*args, **kwargs):
        # Your webhook validation logic here
        return await f(*args, **kwargs)
    return decorated_function
```

#### app/handlers/push_handler.py (and similar for other handlers)

```python
async def handle(request):
    payload = await request.json
    # Your push event logic here
    return jsonify({'msg': 'Push event received'}), 200
```

### Additional Points

1. **Logging**: Implement proper logging for debugging and monitoring.
2. **Error Handling**: Add global or local error handlers to deal with exceptions gracefully.
3. **Rate Limiting**: If needed, implement rate limiting to prevent abuse.
4. **Authentication and Security**: Implement proper authentication mechanisms to ensure only authorized services can access your endpoints.

This example should give you a solid foundation to start building your GitHub webhook event handler with Quart.
