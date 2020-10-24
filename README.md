# DataMining Data

This help me quickly go through course materials in google colab

```python
import io
import requests

url_UsedCar_MissingValue = 'https://raw.githubusercontent.com/rfcpdq/DataMining/master/Lasso/UsedCar_MissingValue.csv'

f = requests.get(url_UsedCar_MissingValue).content
df = pd.read_csv(io.StringIO(f.decode('utf-8')))
```
