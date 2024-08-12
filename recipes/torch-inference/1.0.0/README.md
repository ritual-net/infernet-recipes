## Torch Inference Service

### Description

Serves inference on **Pytorch** models. [PyTorch](https://pytorch.org/) is an open source deep learning framework that provides a flexible platform for building and deploying machine learning models. This service allows you to deploy and run models for various tasks.

For configuration and usage details, check out the [Pytorch Inference Service](https://infernet-services.docs.ritual.net/reference/torch_inference_service) documentation.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "torch-inference_1.0.0",
    "recipe_vars": {
        "MODEL_SOURCE": <your_value_here>, // OPTIONAL
        "LOAD_ARGS": <your_value_here>,    // OPTIONAL
        "USE_JIT": <your_value_here>,      // OPTIONAL
        "TEST_ENV": <your_value_here>,     // OPTIONAL
        "NUM_WORKERS": <your_value_here>,  // OPTIONAL
    }
}
```

**Note** that any configurations must be included in `recipe_vars`.