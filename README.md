# Team Communication Network Viewer
*This is supposed to be a code to plot relationships between colleagues within a team in a very visible manner*

## Motivation
Team communications is usually a recurring problem between colleagues, and sometimes only the qualitative perceptions aren't enough to identify possible problems and isolated professionals, leading to turnovers and bad teamwork. 

This tool is supposed to be a plotter for a technique applied within a large-sized company that follows the Spotify Organization Model (tribes and squads).

A communication matrix is built through HR research on self-declared connection perceptions between teammembers (columns), thus making rows the overall perceived communications from third parties within the same team.

This is highly valuable to assess if the team members are aware of their roles and importances, and identify strong and weak points to act locally. It is also possible to compare different team performances regarding this subject.

## Quick start
Function using is straightforward as described in docstrings.

The input matrix has to be in the format name vs name, like the figure below. It will only work if the names are correspondent and equal.
![image](https://user-images.githubusercontent.com/81642424/135534333-d2db771a-97ef-4fb8-9026-4139734d108e.png)

The relationships follow the list:
<ol>
  <li>0.5: weak perceived connection</li>
  <li>1.0: average perceived connection</li>
  <li>2.0: strong perceived connection</li>
</ol>

Data is collected through HR research, asking each person to fill up a form asking to rank their relationships to other team members like aforementioned.

For the code to work, data above have to be transformed to the following format:
![image](https://user-images.githubusercontent.com/81642424/135534624-9dda6ecc-99be-4375-a359-1d158d96b5a5.png)

So, data can be wrangled like that:

```python
# wrangle for the hive team
df_hive = pd.read_excel('conexoes_hive.xlsx')
df_hive = addColors(df_hive)
df_hive = meltMatrix(df_hive)
df_hive.head()
```

And, for the actual network:
```python
plotNetwork(df_hive,out_name='hive_single_color')
```
Which will lead to the following result:

![hive_single_color](https://user-images.githubusercontent.com/81642424/135535016-92883efe-f9f2-4e87-95fb-d5661913ee9e.png)

## Installation files
This code uses following python packages and distributions (ran in 3.8.5):
```python
# data analysis
import pandas as pd 
import numpy as np

# pseudo random generator
import random

# plotters
import matplotlib.pyplot as plt
import networkx as nx
```

## Creator
Copyright Daniel Leto (dletoneiva@gmail.com). Please follow me on Twitter and Medium (@dletoneiva).
