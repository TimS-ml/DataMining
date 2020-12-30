# DataMining Data

I'm TA of data mining for business course in Fordham University winter 2020
This repo helps me quickly load data in google colab

```python
import io
import requests

url = 'https://raw.githubusercontent.com/TimS-ml/DataMining/master/0_TakeHome/0x01_conversion_project.csv'

f = requests.get(url).content
df = pd.read_csv(io.StringIO(f.decode('utf-8')))
```
