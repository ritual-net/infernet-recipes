## TGI Client Inference Service

### Description

This service enables ML inference requests via HuggingFace's [Text Generation Inference (TGI)](https://huggingface.co/docs/text-generation-inference/en/index) API, which serves Large Language Models (LLMs).

### Configurations

- `TGI_SERVICE_URL` (`string`)
  - The TGI service URL.
- `HF_TOKEN` (`string`)
  - The HuggingFace [API Token](https://huggingface.co/docs/hub/en/security-tokens).
- `CONNECTION_TIMEOUT` (`number`, `optional`)
  - The connection timeout in seconds. Defaults to `30`.
- `RETRY_PARAMS` (`object`, `optional`)
  - The retry parameters for the inference workflow. Defaults to `{}`.
- `NUM_WORKERS` (`number`, `optional`)
  - The number of workers to use with the server. Defaults to `2`.

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

**Note** that your [configurations](#configurations) must be included in `recipe_vars`.
