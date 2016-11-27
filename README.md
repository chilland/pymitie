# pymitie-docker

A python2 base image with [MITIE](https://github.com/mit-nlp/MITIE) built in.
Uses [this](https://github.com/openeventdata/mitie-py) setup code for the MITIE
python wrapper.

## Usage
Download the models you wish to use and mount them as a volume. Then use mitie
as you would normally in python. the library itself is installed in
`/usr/src/MITIE/mitielib`.

``` 
wget https://github.com/mit-nlp/MITIE/releases/download/v0.4/MITIE-models-v0.2.tar.bz2
tar --no-same-owner -xjf MITIE-models-v0.2.tar.bz2 
docker run -ti -v /LOCAL/PATH/TO/MODELS/MITIE-models:/usr/src/MITIE-models --rm chilland/pymitie:v0.0.1 python2
```

```python 
from mitie import *

ner = named_entity_extractor('/usr/src/MITIE/MITIE-models/english/ner_model.dat')
```
