# Azure OpenAI Python Project

This project demonstrates how to use the Azure OpenAI API with Python to interact with a chat model. It uses an API key for authentication, loaded from a `.env` file.

## Prerequisites

*   Python (3.7+ recommended)
*   pip (Python package installer)
*   Git (for cloning the repository)

## Getting Started

1.  **Clone the repository (if you haven't already):**
    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  **Create and activate a virtual environment (recommended):**
    *   On macOS and Linux:
        ```bash
        python3 -m venv .venv
        source .venv/bin/activate
        ```
    *   On Windows:
        ```bash
        python -m venv .venv
        .\.venv\Scripts\activate
        ```

3.  **Install dependencies:**
    The project dependencies are listed in `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```
    Alternatively, you can use the provided shell script:
    ```bash
    sh install.sh  # For Linux/macOS
    # For Windows, you might need to execute the pip command directly as above.
    ```

4.  **Configure Environment Variables:**
    This project uses a `.env` file to manage sensitive information like your API key.
    *   Create a file named `.env` in the root directory of the project.
    *   Add your Azure OpenAI subscription key to the `.env` file:
        ```env
        SUBSCRIPTION_KEY="YOUR_AZURE_OPENAI_SUBSCRIPTION_KEY"
        ```
        Replace `YOUR_AZURE_OPENAI_SUBSCRIPTION_KEY` with your actual key.
    *   **Important:** The `.env` file is included in `.gitignore` and should *not* be committed to version control.

    The script `run_model.py` is pre-configured with the following default values, which can also be overridden by setting them in your `.env` file if needed:
    *   `ENDPOINT_URL="https://ps-swe-openai.openai.azure.com/"`
    *   `DEPLOYMENT_NAME="o4-mini"` (this is used as `model` in the script)

## Running the Model

Once you have completed the setup steps, you can run the model:

```bash
python run_model.py
```

The script will send a predefined prompt to the Azure OpenAI chat model and print the assistant's response to the console.

## Authentication

This project uses API key authentication. The `AzureOpenAI` client in `run_model.py` is configured to use the `SUBSCRIPTION_KEY` loaded from your `.env` file.

Ensure your `.env` file is correctly set up as described in the "Configure Environment Variables" section. 