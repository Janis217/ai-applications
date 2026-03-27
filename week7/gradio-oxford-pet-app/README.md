# Gradio Oxford Pet App

This app compares 3 image classification approaches on pet images:

- Fine-tuned ViT model (`kuhs/pokemon-vit`)
- Zero-shot CLIP (`openai/clip-vit-large-patch14`)
- OpenAI vision model (LLM image classification)

## Dataset Used For Training

- Hugging Face dataset loader: `load_dataset("pcuenq/oxford-pets")`
- Kaggle dataset reference: https://www.kaggle.com/datasets/tanlikesmath/the-oxfordiiit-pet-dataset

## Trained Model

- Hugging Face model link: https://huggingface.co/kuhs/pokemon-vit

## Training Performance

| Epoch | Step | Validation Loss | Accuracy |
|---|---:|---:|---:|
| 1.0 | 10 | 1.8412 | 0.2105 |
| 2.0 | 20 | 1.6505 | 0.3684 |
| 3.0 | 30 | 1.5253 | 0.6316 |
| 4.0 | 40 | 1.4592 | 0.6316 |
| 5.0 | 50 | 1.4373 | 0.6316 |

## Example Image Results

The table below reports the true class and Top-3 predictions for ViT and CLIP.

| Image | True Class | ViT Top-3 (score) | CLIP Top-3 (score) | OpenAI LLM (label, confidence) |
|---|---|---|---|---|
| `dog1.jpg` | `golden retriever` | `great pyrenees` (0.6276)<br>`newfoundland` (0.0863)<br>`shiba inu` (0.0655) | `english cocker spaniel` (0.1701)<br>`great pyrenees` (0.1505)<br>`boxer` (0.1277) | `golden retriever` (0.0) |
| `dog2.jpg` | `german shorthaired` | `leonberger` (0.2244)<br>`keeshond` (0.1889)<br>`shiba inu` (0.1467) | `leonberger` (0.5678)<br>`scottish terrier` (0.1460)<br>`boxer` (0.0842) | `german shorthaired` (0.3) |
| `leonberger.jpg` | `leonberger` | `leonberger` (0.9995)<br>`newfoundland` (0.0001)<br>`saint bernard` (0.0001) | `leonberger` (0.9992)<br>`saint bernard` (0.0006)<br>`keeshond` (0.0002) | `leonberger` (0.95) |
| `cat.jpg` | `Egyptian Mau` | `Egyptian Mau` (0.8122)<br>`Bengal` (0.1527)<br>`Maine Coon` (0.0256) | `Egyptian Mau` (0.3501)<br>`British Shorthair` (0.3041)<br>`Maine Coon` (0.0995) | `Egyptian Mau` (0.7) |
| `snow_leopard.jpeg` | `Snow Leopard` | `Egyptian Mau` (0.4866)<br>`Bengal` (0.3089)<br>`english setter` (0.0340) | `Bengal` (0.6542)<br>`Ragdoll` (0.2521)<br>`Persian` (0.0499) | `Bengal` (0.6) |