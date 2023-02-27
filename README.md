# CUHK_STAT1013
report about the final project to CUHK-STAT1013
# **CUHK-STAT1013-ProjA**
---
>name: Una, Shengyuan Zhong
>
>student ID: 1155156303
>
>email : <1155156303@link.cuhk.edu.hk>
---
## table of contents
1. [Topic](##Topic)
2. [Hypothesis](##Hypothesis)
3. [Prepare](##Prepare)
---
## Topic: Stock price forecasting of Nintendo and Amazon
- **Description**
>Dataset describing the Amazon and Nintendo's Stock price.
- **Github**
>https://github.com/unamiki66/CUHK_STAT1013

- **CSV dataset from**
>[yahoo!finance](https://finance.yahoo.com/)
- **Sample size:**
>506
- **Feature documentation:**
> ![](https://i.imgur.com/gZicob4.png)
---
## Hypothesis
- **Tell us what your idea is and why you have chosen to pursue this idea.**
> I am interestes in "*Which Stock price people buying/using in the same time period , Nintendo or Amazon?*"
- **What two groups you are comparing:**
> **G1**:opening Stock price of Amazon
> **G2**:opening Stock price of Nintendo
- **What you will be measuring (i.e., what your response variable will be):**
> **open**
- **Is your response variable quantitative rather than categorical?**
> **open** is integer data,which can be regarded as a quantitative variable.
- **Make a prediction about what kind of difference you expect to see between your samples and WHY.**
> I expect that **G1**>**G2**, because Amazon is a shopping website, people may spend more money on Amazon's website to shop for some real-life products than Nintendo's game .
- **Talk about how you will gather your data**
> From yahoo!finance link:
> 1. https://finance.yahoo.com/quote/AMZN?p=AMZN&.tsrc=fin-srch
>  2. https://finance.yahoo.com/quote/NTDOY?p=NTDOY&.tsrc=fin-srch
>  
>From Github link:
>1. https://github.com/unamiki66/CUHK_STAT1013
- **If you had unlimited resources (time, money, staff, etc.) how would you collect your data?**
>1. Getting more time periods' information
>2. Try collecting more hits from different applications.
---
## Prepare
```python=
import numpy as np
import pandas as pd

df = pd.read_csv('./una-stat1013 data .csv')
df.head(5)

(df[df['Type'] == 'Amazon']['Open']).head(5)
(df[df['Type'] == 'Nintendo']['Open']).head(5)

print(df[df['Type'] == 'Nintendo']['Open'].mean())
print(df[df['Type'] == 'Amazon']['Open'].mean())

import seaborn as sns
import matplotlib.pyplot as plt

sns.lineplot(data=df, x="Date", y="Open", hue='Type')
plt.show()
