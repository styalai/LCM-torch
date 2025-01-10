# LCM-torch
A simple and easy to use implementation of a Large Concept Model with pytorch.

# Install
```
pip install git+https://github.com/styalai/LCM-torch
pip install -q wtpsplit
```
You also need to install faiseq2 but there are two command:
- With GPU
```
pip install -q fairseq2==v0.3.0rc1 --pre --extra-index-url  https://fair.pkg.atmeta.com/fairseq2/whl/rc/pt2.5.1/cu124 --upgrade
```
- With CPU (you also need to install torch for CPU ONLY
```
pip install fairseq2==v0.3.0rc1 --pre --extra-index-url  https://fair.pkg.atmeta.com/fairseq2/whl/rc/pt2.5.1/cpu
```
And install SONAR.
```
pip install sonar-space
```
All (for GPU):
```
pip install git+https://github.com/styalai/LCM-torch
pip install -q wtpsplit
pip install -q fairseq2==v0.3.0rc1 --pre --extra-index-url  https://fair.pkg.atmeta.com/fairseq2/whl/rc/pt2.5.1/cu124 --upgrade
pip install sonar-space
```
# Use

```python
class LCMConfig:
    def __init__(self):
        self.device = "cuda"
        # Transformer args
        self.embd_dim = 1024 # dim of sonar embeddings
        self.dim = 512 # dim of the transformer
        self.layers = 3
        self.heads = 8
    
        # Sonar args
        self.lang = "eng_Latn"
        self.max_seq_len = 512
        self.sonar_enc = "text_sonar_basic_encoder"
        self.sonar_dec = "text_sonar_basic_decoder"
    
        # wtpsplit args
        self.model_name = "sat-1l-sm"
        self.threshold = 0.05

config = LCMConfig()
lcm = LCMModel(config)

o = lcm.generate("hello", num_generated_concepts=2)
```
# Messages
If you like this repo you can <b>put a star</b>.
And if you want to understand the implementation I created an article:\n
-> link

# Citation
If you use LCM-torch in your research or projects, please cite the original Large Concept Model paper:
```
@article{lcm2024,
  author = {{LCM team}, Lo\"{i}c Barrault, Paul-Ambroise Duquenne, Maha Elbayad, Artyom Kozhevnikov, Belen Alastruey, Pierre Andrews, Mariano Coria, Guillaume Couairon, Marta R. Costa-juss\`{a}, David Dale, Hady Elsahar, Kevin Heffernan, Jo\~{a}o Maria Janeiro, Tuan Tran, Christophe Ropers, Eduardo Sánchez, Robin San Roman, Alexandre Mourachko, Safiyyah Saleem, Holger Schwenk},
  title = {{Large Concept Models}: Language Modeling in a Sentence Representation Space},
  publisher = {arXiv},
  year = {2024},
  url = {https://arxiv.org/abs/2412.08821},
}
```
