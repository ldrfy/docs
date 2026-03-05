## Quick Start

1. Install and start the Ollama service

    > Make sure http://127.0.0.1:11434 is reachable. See the Ollama official website: https://ollama.com/

    ```bash
    ollama serve
    ```

2. Install the model `translategemma:4b`

    ```bash
    ollama run translategemma:4b
    ```

3. Call the translation engine with a single-line config string:

    > The default values usually do not need changes. See the parameter details below for customization.


## Parameters

```bash
http://127.0.0.1:11434  |  translategemma:4b  |  You are a translation engine. Only output the translated text.  |  Translate the following text from {from_lang} to {to_lang}:\n{text}  |  temperature=0.2;top_p=0.9;timeout=60
```

The engine configuration uses one string with five parameter segments separated by `|`, with the following meanings:

1. `http://127.0.0.1:11434`
   - Meaning: Ollama service address (HTTP API).
   - Note: Usually does not need to be changed.

2. `translategemma:4b`
   - Meaning: Model name to use.
   - Note: Make sure the model is available in Ollama.

3. `You are a translation engine. Only output the translated text.`
   - Meaning: System prompt to constrain model behavior.
   - Note: Output only the translation without extra content.

4. `Translate the following text from {from_lang} to {to_lang}:\n{text}`
   - Meaning: User prompt template.
   - Note: `{from_lang}`, `{to_lang}`, and `{text}` are replaced at runtime.

5. `temperature=0.2;top_p=0.9;timeout=60`
   - Meaning: Inference and request options.
   - Note:
     - `temperature`: Sampling temperature; lower is more stable.
     - `top_p`: Nucleus sampling threshold; controls diversity.
     - `timeout`: Request timeout (seconds).
