# 상위 유튜브 채널 top 1000 분석
프로젝트 설명
이번 프로젝트의 주제는 데이터를 분석해서 python의 seaborn, matplotlib, numpy, pandas 등의 외부 라이를 이용하여 그래프를 그리는 것인데 여러 데이터 사이트를 검색하던 중 kaggle에서 이번 프로젝트를 위한 데이터 분석 자료로 하기에 흥미로운 데이터를 찾았다. 그 데이터는 상위 유튜브 채널 top 1000에 대한 데이터였는데 top 1000 유튜브 채널에 대해 분석해보는 것은 너무 재미있을 것 같아서 진행하게 되었다. 일단 상위 유튜브 채널 top 1000의 데이터 중 분석한 것으로는 top 1000의 유튜브 채널이 어떤 유형의 채널인지를 분석해보았다. 그리고 그것을 동아리 시간 중 데이터 분석 부분에서 배운  python의 seaborn, matplotlib, numpy, pandas 등의 외부 라이브러리를 이용하여 막대 그래프로 나타내어 보았다. 또한 top 1000 유튜브 채널이 어느 국가에서 몇 개 속해 있는지를 분석해보았다. 그리고 그것을 동아리 시간 중 데이터 분석 부분에서 배운 python의 seaborn, matplotlib, numpy, pandas 등의 외부 라이브러리를 이용하여 원 그래프로 나타내어 보았다.
1) 국가별 top 1000 채널 수
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from google.colab import files
files.upload()
df = pd.read_csv('Youtuber.csv')
country_counts = df['Country'].value_counts()
plt.figure(figsize = (12, 6))
country_counts.plot(kind = 'bar', color = 'skyblue')
plt.title('Count of Channels by Country')
plt.xlabel('Country')
plt.ylabel('Number of Channels')
plt.show()
```
<img width="789" alt="image" src="https://github.com/user-attachments/assets/ed9ea7b7-3020-4adc-ad1f-5f42129d441b">

country_counts를 통해 country 항목에 있는 값을 가져오고, plt.figure를 통해 그래프 크기를 정한 후, ~.plot을 통해 데이터를 막대그래프로 나타내었다. 

2) 국가별 top 1000 채널 비율
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from google.colab import files
files.upload()
df = pd.read_csv('Youtuber.csv')
category_counts = df['Country'].value_counts()
plt.figure(figsize = (12, 6))
plt.pie(category_counts, labels = category_counts.index, autopct = '%1.1f%%', startangle = 90)
plt.title('Distribution of Channels by Country')
plt.show()
```
<img width="422" alt="image" src="https://github.com/user-attachments/assets/152d0499-f735-4a47-a171-f70ca0c0cc13">

category_counts를 통해 country 항목에 있는 값을 가져온 후, plt.figure로 그래프의 크기를 정한 후, plt.pie를 통해 데이터를 원그래프로 나타내었다.

3) 국가별 top 1000 채널의 수(가로 형태의 막대그래프)
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from google.colab import files
files.upload()
df = pd.read_csv('Youtuber.csv')
country_counts = df['Country'].value_counts()
plt.figure(figsize = (12, 6))
country_counts.plot(kind = 'barh', color = 'yellow')
plt.title('Count of Channels by Country')
plt.xlabel('Number of Channels')
plt.ylabel('Country')
plt.show()
```
<img width="836" alt="image" src="https://github.com/user-attachments/assets/7a1dc467-9714-44fe-866b-f6897e7b1366">

country_counts를 통해 country 항목에 있는 값을 가져오고, plt.figure를 통해 그래프 크기를 정한 후, ~.plot을 통해 데이터를 가로 형태의 막대그래프로 나타내었다.
