## 最简使用方案

1. 安装并启动 Ollama 服务

    > 确保 [http://127.0.0.1:11434](http://127.0.0.1:11434)可访问。详见 [Ollama 官网](https://ollama.com/)

    ```bash
    ollama serve
    ```

2. 安装模型 `translategemma:4b`

    ```bash
    ollama run translategemma:4b
    ```

3. 使用单行配置字符串调用翻译引擎：

    > 默认值一般不需要修改，具体可以看下面参数说明进行定制


## 参数说明

```bash
http://127.0.0.1:11434  |  translategemma:4b  |  You are a translation engine. Only output the translated text.  |  Translate the following text from {from_lang} to {to_lang}:\n{text}  |  temperature=0.2;top_p=0.9;timeout=60
```

引擎配置使用 1 个字符串，内部包含 5 个参数段，使用 `|` 分隔，对应如下含义：

1. `http://127.0.0.1:11434`
   - 含义：Ollama 服务地址（HTTP API）。
   - 说明：一般不需要修改。

2. `translategemma:4b`
   - 含义：使用的模型名称。
   - 说明：需确保该模型已在 Ollama 中可用。

3. `You are a translation engine. Only output the translated text.`
   - 含义：系统提示词，用于约束模型行为。
   - 说明：要求只输出译文，不添加多余内容。

4. `Translate the following text from {from_lang} to {to_lang}:\n{text}`
   - 含义：用户提示词模板。
   - 说明：`{from_lang}`、`{to_lang}`、`{text}` 会在运行时被替换。

5. `temperature=0.2;top_p=0.9;timeout=60`
   - 含义：推理与请求参数。
   - 说明：
     - `temperature`：采样温度，越低越稳定。
     - `top_p`：核采样阈值，控制多样性。
     - `timeout`：请求超时（秒）。
