
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
IPL Data
df=pd.read_csv('iplauction2023.csv')
df
name	player style	nationality	base price (in lacs)	final price (in lacs)	franchise	status
0	Harshit Rana	Bowler	India	NaN	20.0	KKR	RETAINED
1	Ekant Sen	Batter	India	20.0	NaN	NaN	UNSOLD
2	Wayne Parnell	Allrounder	South Africa	75.0	NaN	NaN	UNSOLD
3	Shakib Al Hasan	Allrounder	Bangladesh	150.0	150.0	KKR	SOLD
4	Joe Root	Batter	England	100.0	100.0	RR	SOLD
...	...	...	...	...	...	...	...
304	MS Dhoni	WK-Batter	India	NaN	1200.0	CSK	RETAINED
305	Moeen Ali	Allrounder	England	NaN	800.0	CSK	RETAINED
306	Ruturaj Gaikwad	Batter	India	NaN	600.0	CSK	RETAINED
307	Rishabh Pant	WK-Batter	India	NaN	1600.0	DC	RETAINED
308	Axar Patel	Allrounder	India	NaN	900.0	DC	RETAINED
309 rows × 7 columns

ndf=df['player style'].value_counts().reset_index()
ndf
player style	count
0	Bowler	111
1	Allrounder	103
2	Batter	55
3	WK-Batter	40
plt.figure(figsize=(5,5),facecolor='green')

plt.title('Types of Player')
plt.xlabel('Style')
plt.ylabel('Count')
plt.grid()

plt.bar(ndf['player style'],ndf['count'],label='Player Type',color='pink')
plt.legend()
plt.savefig('Covid scatter.png')

ndf
player style	count
0	Bowler	111
1	Allrounder	103
2	Batter	55
3	WK-Batter	40
plt.figure(figsize=(5,5),facecolor='pink')
plt.pie(ndf['count'],labels=ndf['player style'],autopct='%.2f%%')

plt.show()

 
