# pytorch-randaugment
Unofficial PyTorch Reimplementation of AutoAugment and RandAugment.

Code taken from https://github.com/DeepVoltaire/AutoAugment and https://github.com/jizongFox/uda
## How to install:
```bash
$ pip install git+https://github.com/seareale/pytorch-randaugment
```
---

## How to use:
```python
from randaugment import RandAugment, ImageNetPolicy
data = ImageFolder(rootdir, transform=transforms.Compose(
                        [
                            transforms.RandomCrop(32, padding=4, fill=128), # fill parameter needs torchvision installed from source
                            transforms.RandomHorizontalFlip(), 
                            RandAugment(),
                            #ImageNetPolicy(),
                            Cutout(size=16), # (https://github.com/uoguelph-mlrg/Cutout/blob/master/util/cutout.py)
                            transforms.ToTensor(), 
                            transforms.Normalize(...)
                        ])
)
loader = DataLoader(data, ...)
```


