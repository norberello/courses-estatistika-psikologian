---
title: 'Estatistika deskribatzailea'
description: "Zentro joerako neurriak, sakabanatze neurriak, asimetria, eta kurtosi neurriak\n"
---

## Datuak ikusi

```yaml
type: NormalExercise
key: 2bafef99a3
lang: r
xp: 100
skills: 1
```

Ikus ditzagun datuak! Normalean datuak orri kalkulo moduan agertuko zaizkigu non zutabe bakoitza aldagai bat den eta lerro bakoitza kasu bat (psikologian normalean pertsona bat). Edozein analisirik egin baino lehenago oso komenigarria da gure datuen natura ezagutzea. Adibide gisa datubase hau erabiliko dugu non pertsona bakoitzak

> Jenkins R, Dowsett AJ, Burton AM (2018) How many faces do people know?. Proceedings of the Royal Society B 285(1888): 20181319

`@instructions`
1. `aurpegiak` datubasea kargatuta daukazu, ikus ditzazu datuak `print()` komandoa erabilita
2. pista bat nahi baduzu sakatu `hint`

`@hint`
bakarrik "submit answer" sakatu, ez duzu besterik egin behar :)

`@pre_exercise_code`
```{r}
aurpegiak <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
```

`@sample_code`
```{r}
#aurpegiak datubasea ikusi
print(aurpegiak)
```

`@solution`
```{r}
print(aurpegiak)
```

`@sct`
```{r}
test_error()
success_msg("hasera ona, orain badakizu nola funtzionatzen duen")
```
