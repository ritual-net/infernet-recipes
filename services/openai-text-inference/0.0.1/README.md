## OpenAI Text Inference

### Description

This service enables querying the OpenAI [completions](https://platform.openai.com/docs/guides/text-generation/chat-completions-api) and [embeddings](https://platform.openai.com/docs/guides/embeddings) APIs.

### Requirements

- An OpenAI [Account](https://platform.openai.com/)
- An OpenAI [API key](https://platform.openai.com/api-keys)

### Configurations

- **OPENAI_API_KEY**: The OpenAI API Key
- NUM_WORKERS (optional): The number of workers to use with the server.
    - Defaults to `2`.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "openai-text-inference_0.0.1",
    "recipe_vars": {
        "OPENAI_API_KEY": <your_value_here>,
        "NUM_WORKERS": <your_value_here>, // OPTIONAL
    }
}
```

**Note** that your [configurations](#configurations) must be included in `recipe_vars`.

### Input Data

**Request data**:
```js
{
    "model": string,
    "params": CompletionParams | EmbeddingParams
}
```

<blockquote>
    ℹ️ <strong> Important:</strong> Model names are different for Completions and Embeddings. Refer to OpenAI's <a href="https://platform.openai.com/docs/models/model-endpoint-compatibility">model endpoint compatibilty</a> page for the latest models available via API.
</blockquote>


**CompletionParams**
```js
{
    "endpoint": "completions",
    "messages": {
        "role": "system" | "assistant" | "user" | "function",
        "content": string
    }[]
}
```

**EmbeddingParams**
```js
{
    "endpoint": "embeddings",
    "input": string
}
```