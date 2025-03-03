![image](https://github.com/user-attachments/assets/56b7da2e-9559-4b79-874b-13b8504fe7bf)LLMManager

A Swift-based manager for downloading and running a local LLM (TinyLlama-1.1B-Chat-v1.0-GGUF) using the SpeziLLM framework on iOS.

Current Issue

During response generation, the model file is reported as missing or inaccessible, despite a successful download. Below is a key excerpt from the debug log:

SpeziLLMLocal: Local LLM file could not be opened, indicating that the model file doesn't exist
❌ Response Generation Error: LLM file not found.

Debug Log Excerpt

...
🚀 Model download started
...
✅ Download completed, temporary path: /private/var/mobile/Containers/Data/...
✅ File moved successfully: /var/mobile/Containers/Data/...
📊 Saved model file size: 637699456 bytes
...
SpeziLLMLocal: Local LLM file could not be opened, indicating that the model file doesn't exist
❌ Response Generation Error: LLM file not found.
