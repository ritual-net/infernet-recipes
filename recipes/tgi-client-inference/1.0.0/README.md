## TGI Client Inference Service

### Description

This service enables ML inference requests via HuggingFace's [Text Generation Inference (TGI)](https://huggingface.co/docs/text-generation-inference/en/index) API, which serves Large Language Models (LLMs).

For configuration and usage details, check out the [TGI Client Inference Service](https://infernet-services.docs.ritual.net/reference/tgi_client_inference_service) documentation.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "tgi-client-inference_1.0.0",
    "recipe_vars": {
        "TGI_SERVICE_URL": <your_value_here>,
        "HF_TOKEN": <your_value_here>,
        "CONNECTION_TIMEOUT": <your_value_here>,  // OPTIONAL
        "RETRY_PARAMS": <your_value_here>,        // OPTIONAL
        "NUM_WORKERS": <your_value_here>,         // OPTIONAL
    }
}
```

**Note** that any configurations must be included in `recipe_vars`.