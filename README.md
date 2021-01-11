# DataMining Data

I'm TA of data mining for business course in Fordham University winter 2020
This repo helps me quickly load data in google colab

```python
import io
import requests
import gzip

# Example 1
url = 'https://raw.githubusercontent.com/TimS-ml/DataMining/master/0_TakeHome/0x01_conversion_project.csv'
f = requests.get(url).content
df = pd.read_csv(io.StringIO(f.decode('utf-8')))

# Example 2
url = 'https://github.com/TimS-ml/DataMining/blob/master/z_Other/diabetes.csv.gz?raw=true'
f = requests.get(url).content
data = np.loadtxt(gzip.open(io.BytesIO(f), 'rt'),
                  delimiter=',', dtype=np.float32)

# Example 3
url = 'https://github.com/TimS-ml/DataMining/blob/master/z_Other/diabetes.csv.gz?raw=true'
filename = url.split('/')[-1].split('?')[0]
with open(filename, "wb") as f:
    r = requests.get(url)
    f.write(r.content)
```
