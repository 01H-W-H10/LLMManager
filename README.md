LLMManager

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



Debuging

LLMManager initialized
Loading module(s) LLMRunner ...
Loading module(s) LLMManager ...
Model storage path: /var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMModels
Attempt to present <UIAlertController: 0x1026a4c00> on <_TtGC7SwiftUI19UIHostingControllerGVS_15ModifiedContentVS_7AnyViewVS_12RootModifier__: 0x101939340> (from <_TtGC7SwiftUI19UIHostingControllerGVS_15ModifiedContentVS_7AnyViewVS_12RootModifier__: 0x101939340>) which is already presenting <UIAlertController: 0x1026a5200>.

=== Starting model download ===
📥 Download URL: https://huggingface.co/TheBloke/TinyLlama-1.1B-Chat-v1.0-GGUF/resolve/main/tinyllama-1.1b-chat-v1.0.Q4_0.gguf
📂 Download directory: /var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMDownloads
✅ Download directory created
📄 Model file save path: /var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMDownloads/tinyllama-1.1b-chat-v1.0.Q4_0
🚀 Model download started - updating UI
✅ Download task started
⏳ Download progress: 10%
⏳ Download progress: 20%
⏳ Download progress: 30%
⏳ Download progress: 40%
⏳ Download progress: 50%
⏳ Download progress: 60%
⏳ Download progress: 70%
⏳ Download progress: 80%
⏳ Download progress: 90%
✅ Download response code: 200
📊 Content size: 637699456 bytes
⏳ Download progress: 100%
✅ Download complete, temporary path: /private/var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/tmp/CFNetworkDownload_IuRSUD.tmp
✅ File move complete: /var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMDownloads/tinyllama-1.1b-chat-v1.0.Q4_0
📊 Saved model file size: 637699456 bytes
🔄 Attempting to load the downloaded model
Model storage path: /var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMModels
📂 Downloaded model path: /var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMDownloads/tinyllama-1.1b-chat-v1.0.Q4_0
✅ Schema details: LLMLocalSchema(parameters: SpeziLLMLocal.LLMLocalParameters(systemPrompt: Optional("You are a helpful, respectful and honest assistant. Always answer as helpfully as possible, while being safe and still concise. Your answers should not include any harmful, unethical, racist, sexist, toxic, dangerous, or illegal content. Please ensure that your responses are socially unbiased and positive in nature. If a question does not make any sense, or is not factually coherent, explain why instead of answering something not correct. If you don't know the answer to a question, please don't share false information."), maxOutputLength: 512, extraEOSTokens: Set([]), displayEveryNTokens: 4, seed: nil, chatTemplate: nil), samplingParameters: SpeziLLMLocal.LLMLocalSamplingParameters(topP: 1.0, temperature: 0.6, penaltyRepeat: nil, repetitionContextSize: 20), injectIntoContext: false, configuration: MLXLMCommon.ModelConfiguration(id: MLXLMCommon.ModelConfiguration.Identifier.id("/var/mobile/Containers/Data/Application/DB697490-0400-476B-8E57-EBD26B7DA1A8/Documents/LLMDownloads/tinyllama-1.1b-chat-v1.0.Q4_0"), tokenizerId: nil, overrideTokenizer: nil, defaultPrompt: "hello", extraEOSTokens: Set([])))
📝 Generated session info: Optional(SpeziLLMLocal.LLMLocalSession)
🚀 Model load complete! modelLoaded = true
Can't find or decode reasons
Failed to get or decode unavailable reasons
Can't find or decode disabled use cases
<0x10253d680> Gesture: System gesture gate timed out.

=== Starting response generation ===
📂 Currently selected model: tinyllama-1.1b-chat-v1.0.Q4_0.gguf
✅ Checking for existing session
📝 Session info: SpeziLLMLocal.LLMLocalSession
💬 Prompt to be generated: USER: Hi

ASSISTANT: 
✅ Prompt successfully added to context
🔄 Starting token generation...
SpeziLLMLocal: Local LLM is being initialized
SpeziLLMLocal: Local LLM file could not be opened, indicating that the model file doesn't exist
❌ Response generation error: LLM file not found.
