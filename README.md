# LCM-torch
A simple and easy to use implementation of a Large Concept Model with pytorch.

# Install
```
pip install git+https://github.com/styalai/LCM-torch
pip install wtpsplit
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
