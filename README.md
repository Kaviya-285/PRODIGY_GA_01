PRODIGY_GA_01
Text Generation with GPT-2

This project is Task 1 of my Generative AI Internship at Prodigy InfoTech. The goal was to fine-tune GPT-2, a transformer-based language model developed by OpenAI, on a custom text dataset, and generate coherent, contextually relevant text using different decoding strategies.

📌 Task Overview

Train a model to generate coherent and contextually relevant text based on a given prompt. Starting with GPT-2, fine-tune it on a custom dataset to create text that mimics the style and structure of the training data.

🛠️ Tech Stack


Python 3
Google Colab (T4 GPU)
Hugging Face transformers — for loading GPT-2 and running training/generation
PyTorch — underlying deep learning framework


📂 Project Workflow


Load pretrained GPT-2 — loaded the small GPT-2 model (gpt2) and its tokenizer using Hugging Face's transformers library.
Prepare the dataset — used a custom paragraph of text as training data, tokenized it, and split it into fixed-size blocks (block_size=64) using a custom PyTorch Dataset class.
Fine-tune the model — fine-tuned GPT-2 on the custom dataset for 3 epochs using Hugging Face's Trainer API. Training loss dropped from ~4.2 to ~3.1–3.5, confirming the model learned from the data.
Save the fine-tuned model — saved the fine-tuned weights and tokenizer locally.
Generate text with different decoding strategies — generated text from the fine-tuned model using four different decoding methods, to compare output quality and coherence (based on the Hugging Face "How to Generate Text" blog).


🔍 Decoding Strategies Compared

StrategyDescriptionSample OutputGreedy SearchAlways picks the most probable next word"The mountains of the mountains of the mountains of the mountains of the world are the most beautiful..." (repetitive)Beam SearchTracks multiple candidate sequences at once, picks the highest overall probability"The mountains in the center of the city were filled with people of all ages, from all walks of life..." (more coherent, less repetitive)Top-K SamplingRandomly samples from the top k most likely next words"The mountains ahead of him and with the great waves, heaving the deep black with his magic..." (more creative/varied)Top-P (Nucleus) SamplingSamples from the smallest set of words whose cumulative probability exceeds p"The mountains are haunted by a sea, showing the hundreds of thousands of good souls who were living in its wisdom..." (natural, most varied)

Key Takeaway

Greedy search produced the most repetitive output, beam search gave more grammatically coherent text, and the sampling-based methods (top-k, top-p) produced the most creative and varied text — consistent with what the Hugging Face reference describes about the tradeoffs between these decoding strategies.

📁 Repository Contents


Text_Generation.ipynb — the complete Colab notebook with all code, outputs, and generated text samples


🚀 How to Run


Open Text_Generation.ipynb in Google Colab
Enable GPU: Runtime → Change runtime type → T4 GPU
Run all cells in order
Modify the text variable in the dataset cell to use your own text if desired


📚 References


How to Generate Text — Hugging Face Blog
aitextgen — Train a GPT-2 Model w/ GPU


Part of the Generative AI Internship Program — Prodigy InfoTech

✍️ Author

Kaviya Sivakumar
