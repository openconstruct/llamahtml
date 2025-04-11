# llamahtml
LLamaHTML is a simple html file to communicate with a running llamacpp llama-server

I dislike the built-in html interface, so I made my own.

simply download the html file, and open in a web browser.

YOU MUST HAVE llama-server running 

![Screenshot From 2025-04-11 17-17-13](https://github.com/user-attachments/assets/bb74768e-a79a-48a2-a909-aa68b1f44342)


## LlamaHTML (Streaming) Documentation

This web app provides a user interface for interacting with a local llama.cpp server, supporting streaming responses.

**Features:**

* **Streaming Responses:**  Receives and renders model output in real-time as it's generated.
* **Markdown Rendering:**  Displays model responses formatted with Markdown, including code highlighting.
* **Code Block Actions:** Copy and download code blocks from model output.
* **Configurable Parameters:** Adjust temperature, max tokens, top-p, top-k, and stop sequences.
* **Theme Switching:** Toggle between light and dark modes.
* **Server URL Management:**  Specify the server URL and optionally save it to local storage.
* **Clear Chat:**  Clears the conversation history.
* **Abort Request:** Cancel in-progress requests.


**Setup:**

1. **Run llama.cpp server:** Start your llama.cpp server locally (or remotely).  Ensure the `/completion` endpoint is accessible. Use `--host 0.0.0.0` if accessing the server from a different machine.
2. **Enter Server URL:**  Provide the full URL of your server in the "Llama Server URL" field.
3. **(Optional) Remember URL:** Check "Remember URL" to store the server URL in your browser's local storage.

**Usage:**

1. **Enter your message:** Type your prompt in the input area.
2. **Send:** Click "Send" or press Ctrl+Enter (Cmd+Enter on macOS) to submit your prompt.
3. **View Response:**  The model's response will stream into the conversation history area.
4. **Configure (Optional):** Use the "Configuration Options" to adjust parameters like temperature and max tokens.
5. **Clear Chat:** Click "Clear Chat" to reset the conversation.
6. **Switch Theme:** Click "Dark"/"Light" to toggle the theme.
7. **Copy/Download Code:** Click the "Copy" or "Download" buttons on code blocks to copy or download code.


**Configuration Options:**

* **Temperature:** Controls randomness (0 - ~2). Higher values = more random output. Default: 0.7
* **Max Predict Tokens (n_predict):** Maximum number of tokens to generate. -1 for infinite. Default: 2048.
* **Top P (0-1):** Nucleus sampling parameter. Default: 0.95
* **Top K (integer):** Top-k sampling parameter. Default: 40
* **Stop Sequences:** Comma-separated strings to stop generation. Default: `USER:, \nUSER:, <|user|>`


**Troubleshooting:**

* **Connection Errors:** Ensure the server is running and the URL is correct. Check the browser console for network errors.
* **Invalid URL Format:** The URL must be a valid HTTP or HTTPS URL (e.g., `http://127.0.0.1:8080`).
* **Empty Message:**  You cannot send empty messages.


**Dependencies:**

* llama-server



**Development:**

The app is built with HTML, CSS, and JavaScript.  The source code is available in the provided HTML file.  You can modify and extend it as needed.

