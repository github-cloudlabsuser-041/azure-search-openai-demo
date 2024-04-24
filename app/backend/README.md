Determining workspace structure

Deciding which workspace information to collect

Gathering workspace info

# [``app/backend``](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Fazureuser%2Fazure-search-openai-demo-1%2Fapp%2Fbackend%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Users\azureuser\azure-search-openai-demo-1\app\backend") Directory

This directory contains the backend code for the application, which is built using [Quart](https://quart.palletsprojects.com/), a Python framework for asynchronous web applications. The frontend and backend communicate using the [AI Chat App HTTP Protocol](https://github.com/Azure-Samples/ai-chat-app-protocol).

## File Structure

- [``app.py``](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Fazureuser%2Fazure-search-openai-demo-1%2Fapp%2Fbackend%2Fapp.py%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Users\azureuser\azure-search-openai-demo-1\app\backend\app.py"): This is the main application file. It contains the application routes and the setup and teardown methods for the application.

## Routes

- `/chat`: This route is used for the chat functionality of the application. It is a POST route that requires authentication.
- `/auth_setup`: This route is a GET route that sends MSAL.js settings to the client UI.
- `/config`: This route is a GET route that sends configuration data to the client.
- `/upload`: This route is a POST route that handles file uploads. It requires authentication.
- `/delete_uploaded`: This route is a POST route that handles deletion of uploaded files. It requires authentication.
- `/list_uploaded`: This route is a GET route that lists uploaded files. It requires authentication.

## Setup and Teardown

- `setup_clients()`: This function is run before the application starts serving. It sets up the necessary clients for the application.
- `close_clients()`: This function is run after the application stops serving. It closes the clients that were set up.

## Customization

The backend can be customized to suit your needs. The primary backend code you'll want to customize is in the [``app/backend/approaches``](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Fazureuser%2Fazure-search-openai-demo-1%2Fapp%2Fbackend%2Fapproaches%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Users\azureuser\azure-search-openai-demo-1\app\backend\approaches") folder, which contains the classes powering the Chat and Ask tabs. Each class uses a different RAG (Retrieval Augmented Generation) approach, which include system messages that should be changed to match your data. For more details, refer to the customization guide.

## Running the Backend

To run the backend, you need to create an instance of the application using the `create_app()` function in [``app.py``](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Fazureuser%2Fazure-search-openai-demo-1%2Fapp%2Fbackend%2Fapp.py%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Users\azureuser\azure-search-openai-demo-1\app\backend\app.py"). Then, you can run the application using Quart's built-in server.
