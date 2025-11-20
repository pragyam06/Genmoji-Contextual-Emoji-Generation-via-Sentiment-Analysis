Open-Genmoji is an open-source recreation of the Genmoji-style emoji generator.
It allows you to generate emojis from text prompts, fine-tune emoji models, experiment with LoRA training, and customize emoji datasets. The project includes scripts for resizing assets, training/fine-tuning, running prompts, and preparing emoji lists.

This repository is intended for developers, ML researchers, and creators interested in exploring emoji generation workflows.

Features

Generate custom emojis from natural-language prompts

Emoji dataset preparation tools

Fine-tune and prune emoji lists

LoRA (Low-Rank Adaptation) support

Configurable pipelines using JSON configs

Includes sample emoji assets for reference

Project Structure
open-genmoji-main/
│
├── assets/
│   ├── banner@dark.png
│   ├── banner@light.png
│   └── genmoji-samples/
│       ├── apple/
│       └── open-genmoji/
│
├── finetuning/
│   ├── config/
│   │   ├── config.json
│   │   └── multidatabackend.json
│   ├── downloadEmojiList.py
│   ├── getEmojiList.py
│   └── pruneEmojiList.py
│
├── lora/
│   ├── README.md
│   ├── LORA_TEMPLATE.md
│   └── info.json
│
├── metaprompt/
│   ├── open-genmoji.md
│   └── open-genmoji.json
│
├── genmoji.py
├── promptAssistant.py
├── resize.py
└── mise.toml

Key Components
1. genmoji.py

Main script for generating Genmoji-style images from prompts.

2. promptAssistant.py

Utility for processing, cleaning, and optimizing prompts.

3. resize.py

Resizes emoji assets for training and dataset formatting.

4. finetuning/

Contains scripts for preparing emoji data lists, pruning duplicates, downloading emoji data, and managing configs.

5. lora/

Templates and metadata for customizable LoRA training.

6. metaprompt/

Includes base prompt structures for generating Genmoji-style outputs.

Installation
1. Clone the repository
git clone https://github.com/your-username/open-genmoji.git
cd open-genmoji

2. Install dependencies

(Add your preferred environment manager if needed)

pip install -r requirements.txt


If no requirements.txt exists, install common dependencies manually:

pip install pillow numpy transformers accelerate torch

Usage
Generate an emoji
python genmoji.py --prompt "cute dragon eating noodles"

Resize emoji dataset
python resize.py --input assets/genmoji-samples --size 512

Prepare emoji list for training
python finetuning/getEmojiList.py

Prune duplicates
python finetuning/pruneEmojiList.py

Fine-Tuning

Configuration files for training are in:

finetuning/config/


To start fine-tuning, use:

python finetuning/train.py --config config/config.json


(If train.py is not included, the config files serve as templates for external training frameworks.)

Samples Included

You can find example emojis inside:

assets/genmoji-samples/


These can be used for:

Testing the generator

Creating datasets

LoRA training

Future Improvements

Model downloading & automatic setup

Training documentation

Web UI for emoji generation

Integrated dataset auto-cleaning

HuggingFace-compatible model card


Author 
Pragya Mundra


Emoji Generation Enthusiast & Developer
Feel free to contribute or open issues!

Contributing

Pull requests are welcome.
Please follow conventional commit style and keep PRs focused.
