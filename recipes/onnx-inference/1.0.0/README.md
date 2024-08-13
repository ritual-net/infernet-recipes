## ONNX Inference Service

### Description

Serves inference on **ONNX** models. [ONNX](https://onnx.ai/) is an open format for representing ML models that enables interoperability between different frameworks and hardware platforms. This service allows you to deploy and run models for various tasks.

For configuration and usage details, check out the [ONNX Inference Service](https://infernet-services.docs.ritual.net/reference/onnx_inference_service) documentation.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "onnx-inference_1.0.0",
    "recipe_vars": {
        "MODEL_SOURCE": <your_value_here>, // OPTIONAL
        "LOAD_ARGS": <your_value_here>,    // OPTIONAL
        "NUM_WORKERS": <your_value_here>,  // OPTIONAL
    }
}
```

**Note** that any configurations must be included in `recipe_vars`.