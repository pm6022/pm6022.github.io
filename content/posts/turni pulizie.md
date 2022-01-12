title: "Turni pulizie"
date: 2022-01-12T15:14:03+01:00
draft: false
toc: false
images:
tags:
  - codice
---

Concepito una mattina noiosa, crea turni di pulizia a due a due partendo da una lista di persone.

```
import random as rd
import datetime as dt

people = ['Angelo', 'Paolo', 'Matteo', 'Gaetano', 'Michele']

rd.shuffle(people)
#print('Random Order:', people)

couples = [(people[i], people[i+1]) for i in range(len(people)-1)]
couples.append((people[-1], people[0]))
#print('Couples:', couples)

today = dt.datetime.now()
#print('Today is the:', today.strftime('%x'))

for j in range(len(couples)):
    nextwk = today + dt.timedelta(days=7*(j+1))
    print('Week:', j+1, nextwk.strftime('%x'))
    print('Couple:', couples[j], '\n')
```
