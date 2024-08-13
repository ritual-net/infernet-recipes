## HF Client Inference Service

### Description

This service enables ML inference requests via HuggingFace's [Inference APIs](https://huggingface.co/docs/api-inference/en/index).

For configuration and usage details, check out the [HF Client Inference Service](https://infernet-services.docs.ritual.net/reference/hf_inference_client_service) documentation.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "hf-client-inference_1.0.0",
    "recipe_vars": {
        "HF_TOKEN": <your_value_here>,
        "NUM_WORKERS": <your_value_here>, // OPTIONAL
    }
}
```

**Note** that any configurations must be included in `recipe_vars`.