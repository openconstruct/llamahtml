# llamahtml
LLamaHTML is a simple html file to communicate with a running llamacpp llama-server

I dislike the built-in html interface, so I made my own.

simply download the html file, and open in a web browser.

YOU MUST HAVE llama-server running 
Features: code blocks that you can copy, source code highlighting, cht bubble interface



# LlamaHTML User Guide 
## 1. Overview

LlamaHTML is a single-file web interface to chat with a locally running `llama.cpp` server. It provides a chat UI, Markdown rendering for responses, code highlighting with copy function, theme switching, and generation parameter controls.

**Requires:** A running `llama.cpp` server with a loaded model. LlamaHTML is just the frontend.

## 2. Setup

1.  **Run Server:** Start your `llama.cpp` server (e.g., `./server -m model.gguf --port 8080`). Note its URL (e.g., `http://127.0.0.1:8080`).
2.  **Open LlamaHTML:** Save the LlamaHTML code as an `.html` file and open it in your browser.
3.  **Enter URL:** Input your server's URL into the "Llama Server URL" field. Optionally check "Remember URL" to save it locally.

## 3. Using the Interface

*   **Server URL:** Connects LlamaHTML to your backend server. The "Send" button activates when the URL format is valid.
*   **Configuration Options:** Expand this section to adjust model generation parameters (see below).
*   **Conversation History:** Displays the chat. Your messages are on the right (blue), model responses on the left (grey).
    *   **Markdown:** Model responses are formatted (lists, bold, etc.).
    *   **Code Blocks:** Code is highlighted. Hover to reveal a "Copy" button.
*   **Status Bar:** Shows loading indicators, success messages, or errors (e.g., connection issues).
*   **Input Area:**
    *   **Your Message:** Type prompts here. `Ctrl+Enter` (or `Cmd+Enter`) sends.
    *   **Send Button:** Submits your message.
    *   **Clear Chat Button:** Clears the displayed conversation history.
*   **Theme Switcher:** Toggles between Light and Dark modes (preference saved locally).

## 4. Configuration Options (Advanced)

Adjust these before sending a message to control the next response:

*   **Temperature (0-2):** Controls randomness. Lower = more focused, Higher = more creative. (Default: 0.7)
*   **Max Predict Tokens:** Max length of the model's reply. `-1` for (potentially) infinite. (Default: 512)
*   **Top P (0-1):** Nucleus sampling. Considers tokens with cumulative probability >= `top_p`. (Default: 0.95)
*   **Top K (int):** Considers only the `top_k` most likely tokens. (Default: 40)
*   **Stop Sequences:** Comma-separated text. Generation stops if the model outputs one of these strings (e.g., `USER:`).

## 5. Troubleshooting

*   **"Connection Error..."**: Check Server URL, ensure `llama.cpp` server is running, check firewalls.
*   **"API Error..."**: Check the Status Bar and the `llama.cpp` server's terminal output for details.
*   **No Response / Stuck:** Server might be slow or processing a long request. Check server terminal. Try a shorter prompt.
*   **Weird Output:** Model-dependent. Try adjusting configuration parameters or prompt phrasing. Check the server's expected prompt format.
*   **UI Glitches:** Check the browser's Developer Console (F12) for errors.

