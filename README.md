# BANER
This is the source code of COLING 2025 paper BANER: Boundary-Aware LLMs for Few-Shot Named Entity Recognition.

## What is BANER 👀
This paper proposes a boundary-aware contrastive learning strategy to enhance the LLM’s ability to perceive entity boundaries for generalized entity spans. Additionally, BANER utilize LoRAHub to align information from the target domain to the source domain, thereby enhancing adaptive cross-domain classification capabilities![image](framework.pdf)

### Local Setup

1. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```
   
### Datasets
Download [datasets](https://pan.quark.cn/s/009015cb519f) and use process_data.ipynb to process raw data, the processed data format is shown as train.json and test.json.


### Models
Download LLMs.


### Training (`myfinetune.py`)

Example usage:

```bash
python myfinetune.py \
    --base_model './models/llama-7b' \
    --data_path './data/GUM/train.json' \
    --output_dir 'lora_finetune'
```

### Inference (`myinference.py`)

Example usage:

```bash
nphup python myinference.py lora_finetune > llama2-lora-cts-GUM_seed42.log
```


If you use the code in your project, please cite the following paper:
COLING'25 ([PDF](https://aclanthology.org/2025.coling-main.691/))
```bibtex
@inproceedings{guo-etal-2025-baner,
    title = "{BANER}: Boundary-Aware {LLM}s for Few-Shot Named Entity Recognition",
    author = "Guo, Quanjiang  and
      Dong, Yihong  and
      Tian, Ling  and
      Kang, Zhao  and
      Zhang, Yu  and
      Wang, Sijie",
    editor = "Rambow, Owen  and
      Wanner, Leo  and
      Apidianaki, Marianna  and
      Al-Khalifa, Hend  and
      Eugenio, Barbara Di  and
      Schockaert, Steven",
    booktitle = "Proceedings of the 31st International Conference on Computational Linguistics",
    month = jan,
    year = "2025",
    address = "Abu Dhabi, UAE",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.coling-main.691/",
    pages = "10375--10389",
    abstract = "Despite the recent success of two-stage prototypical networks in few-shot named entity recognition (NER), challenges such as over/under-detected false spans in the span detection stage and unaligned entity prototypes in the type classification stage persist. Additionally, LLMs have not proven to be effective few-shot information extractors in general. In this paper, we propose an approach called Boundary-Aware LLMs for Few-Shot Named Entity Recognition to address these issues. We introduce a boundary-aware contrastive learning strategy to enhance the LLM`s ability to perceive entity boundaries for generalized entity spans. Additionally, we utilize LoRAHub to align information from the target domain to the source domain, thereby enhancing adaptive cross-domain classification capabilities. Extensive experiments across various benchmarks demonstrate that our framework outperforms prior methods, validating its effectiveness. In particular, the proposed strategies demonstrate effectiveness across a range of LLM architectures. The code and data are released on https://github.com/UESTC-GQJ/BANER."
}
```
Please email to guochance1999@163.com for other inquiries.

### Acknowledgement 💌
This repo is built upon the following work:
**Alpaca-LoRA**
