## CSS Inference Service

### Description

This service enables ML inference requests on select Closed Source models. Currently, the following APIs are supported:
- **OpenAI**'s [completions](https://platform.openai.com/docs/guides/text-generation/chat-completions-api) and [embeddings](https://platform.openai.com/docs/guides/embeddings).
- **GooseAI**'s [completions](https://goose.ai/docs/api/completions).
- **Perplexity**'s [completions](https://docs.perplexity.ai/reference/post_chat_completions).

For configuration and usage details, check out the [CSS Inference Service](https://infernet-services.docs.ritual.net/reference/css_inference_service) documentation.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "css-inference_1.0.0",
    "recipe_vars": {
        "OPENAI_API_KEY": <your_value_here>,        // OPTIONAL
        "GOOSEAI_API_KEY": <your_value_here>,       // OPTIONAL
        "PERPLEXITYAI_API_KEY": <your_value_here>,  // OPTIONAL
        "RETRY_PARAMS": <your_value_here>,          // OPTIONAL
        "NUM_WORKERS": <your_value_here>,           // OPTIONAL
    }
}
```

**Note** that any configurations must be included in `recipe_vars`.