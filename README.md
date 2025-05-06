# BANER
This is the source code of COLING 2025 paper BANER: Boundary-Aware LLMs for Few-Shot Named Entity Recognition.

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
COLING'25 ([PDF](https://arxiv.org/abs/2412.02228))
```bibtex
@inproceedings{guo2025BANER,
  title={BANER: Boundary-Aware LLMs for Few-Shot Named Entity Recognition},
  author={Guo, Quanjiang and Dong, Yihong and Tian, Ling and Kang, Zhao and Zhang, Yu and Wang, Sijie},
  booktitle={COLING 2025: The 31th International Conference on Computational Linguistics},
  year={2025}
}
```
Please email to guochance1999@163.com for other inquiries.
