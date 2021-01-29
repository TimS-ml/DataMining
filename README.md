# DataMining Data

I'm TA of `data mining for business` course in Fordham University winter 2020

This repo helps me quickly load data in google colab

Check `six.moves` if you are using python2

\*.csv
```python
import io
import requests

url = 'https://raw.githubusercontent.com/TimS-ml/DataMining/master/0_TakeHome/0x01_conversion_project.csv'
f = requests.get(url).content
df = pd.read_csv(io.StringIO(f.decode('utf-8')))
```

\*.csv.gz
```python
import io
import requests
import gzip

# Example 1
url = 'https://github.com/TimS-ml/DataMining/blob/master/z_Other/diabetes.csv.gz?raw=true'
f = requests.get(url).content
data = np.loadtxt(gzip.open(io.BytesIO(f), 'rt'),
                  delimiter=',', dtype=np.float32)

# if is .zip file
# z = zipfile.ZipFile(io.BytesIO(r.content))
# z.extractall()

# Example 2
url = 'https://github.com/TimS-ml/DataMining/blob/master/z_Other/diabetes.csv.gz?raw=true'
filename = url.split('/')[-1].split('?')[0]
with open(filename, "wb") as f:
    r = requests.get(url)
    f.write(r.content)
```

\*.wav
```python
import io
from urllib.request import urlopen
import librosa
import soundfile as sf

url = "https://raw.githubusercontent.com/Atcold/pytorch-Deep-Learning/master/res/win_xp_shutdown.wav"
data, samplerate = sf.read(io.BytesIO(urlopen(url).read()))  # this
data, samplerate = librosa.load(io.BytesIO(urlopen(url).read()))  # or this
```

Alternatively
```python
!wget <your url>
!unzip images.zip /content/images/
```
