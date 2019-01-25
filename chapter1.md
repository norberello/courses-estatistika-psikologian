---
title: 'Estatistika deskribatzailea'
description: "Zentro joerako neurriak, sakabanatze neurriak, asimetria, eta kurtosi neurriak\n"
free_preview: true
---

## Datuak ikusi

```yaml
type: NormalExercise
key: 2bafef99a3
lang: r
xp: 100
skills: 1
```

Ikus ditzagun datuak! Normalean datuak orri kalkulo moduan agertuko zaizkigu non zutabe bakoitza aldagai ezberdin bat den eta lerro bakoitza kasu bat. Edozein analisirik egin baino lehenago oso komenigarria da gure datuen natura ezagutzea. Adibide gisa datubase hau erabiliko dugu non pertsona bakoitzak zenbat aurpegi gogoratzen dituen ikertu den:

Jenkins R, Dowsett AJ, Burton AM (2018) How many faces do people know? Proceedings of the Royal Society B 285(1888): 20181319. https://doi.org/10.1098/rspb.2018.1319

`@instructions`
1. `oroimen.data` datu-markoa ("data frame") kargatuta daukazu, ikus ditzazu datuak `print()` komandoa erabilita
2. "**Run Code**" erabiliz esperimentatu dezakezu kodeak daukan irteera, erantzuna daukazunean "**Submit Answer**" sakatu
3. Pista bat nahi baduzu sakatu "**Take Hint**" behean

`@hint`
bakarrik "submit answer" sakatu, ez duzu besterik egin behar lehengo ariketa honetan

`@pre_exercise_code`
```{r}
oroimen.data <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
```

`@sample_code`
```{r}
#aurpegiak datu-markoa ikusi
print(oroimen.data)
```

`@solution`
```{r}
print(oroimen.data)
```

`@sct`
```{r}
success_msg("hasera ona, orain badakizu nola funtzionatzen duen")
```

---

## Aurpegien datubasea miatzen R komanduez

```yaml
type: BulletExercise
key: ef6fa701ab
xp: 100
```

Jarrai dezagun `oroimen.data` datu-markoa miatzen. Badaude R komandu amankomun batzuk hau egiteko, ikas ditzagun bere posibilidadeak datubasea miaketa egiten dugun bitartean.

Ohar orokorrak:

1. **#** sinboloa iruzkinak ipintzeko erabiliko da (honek ez du efekturik kodean)
2. Ordezkatu markatutako azpilerroak beharrezkoa den kodearekin erantzuna lortzeko
3. Edozein unean esperimenta daiteke kontsola lehioan eta baitere kode leioan "Run Code" klik eginez, erantzun zuzenaz seguru zaudenean "Submit Answer"-ri eman eta feedback-a itxaron.

`@pre_exercise_code`
```{r}
oroimen.data <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
```

***

```yaml
type: NormalExercise
key: 49ee500c59
xp: 35
```

`@instructions`
`head()` and `tail()` aginduek lehenego eta azkenengo 6 lerroak aldagien izenburuekin ematen dizkigute besteak beste.

`@hint`
aurpegiak ipini behar den lekuan

`@sample_code`
```{r}
head(aurpegiak)
tail(_________)
```

`@solution`
```{r}
#datuen lehenengo 6 lerroak
head(aurpegiak)
#datuen azkenengo 6 lerroak
tail(aurpegiak)
```

`@sct`
```{r}
success_msg("hasera ona, orain badakizu nola funtzionatzen duen")
```

***

```yaml
type: NormalExercise
key: 18d6469d65
xp: 35
```

`@instructions`
`names()` komandoak aldagien izenak ematen ditu eta dim() datubasearen dimentsioak (zenbat lerro eta zenbat zutabe)

`@hint`
idatzi `?names` kontsolan

`@sample_code`
```{r}
#zeintsuk dira "aurpegiak" datubasearen aldagaien izenak?
names(_______)
#zenbat lerro eta zutabe daude dira "aurpegiak" datubasean?
___(oroimen.data)
```

`@solution`
```{r}
#zeintsuk dira "aurpegiak" datubasearen aldagaien izenak?
names(oroimen.data)
dim(oroimen.data)
```

`@sct`
```{r}
success_msg("hasera ona, orain badakizu nola funtzionatzen duen")
```

***

```yaml
type: NormalExercise
key: cd34a9d446
xp: 30
```

`@instructions`
str() komandoak ("structure") zenbat behaketa eta aldagaiak dauden, eta inportantegoa dena: aldagaien natura diosku.

`@hint`
Idatzi komandoa str eta parentesisen artean datubasearen izena

`@sample_code`
```{r}
#aplikatu str() "aurpegiak" datubaseari:

```

`@solution`
```{r}
str(aurpegiak)
```

`@sct`
```{r}
success_msg("oso ondo, $ sinboloa erabiltzen da aldagaiak banaka identifikatzeko, hurrengo ariketetan ulertuko duzu hobeto")
```

---

## Insert exercise title here

```yaml
type: TabExercise
key: 1aa4f35dcc
xp: 100
```



`@pre_exercise_code`
```{r}

```

---

## Zentro joerako neurriak

```yaml
type: NormalExercise
key: 19b886e4c4
xp: 100
```

Zentro-joerako neurriek datu-multzo bat zein balioren inguruan biltzen den adierazten dute, horren sakabanatzea edo aldakortasuna kontutan hartu barik. Zentro-joerako neurririk amankomunena batezbestekoa da, `mean()`, baina batzutan mediana, `median()`, eta moda ere jakitea komenigarria liteke. 

`@instructions`
Erabili `oroimen.data` datu-markoa kalkulatzeko pertsona batek batezbeste zenbat aurpegi gogora ditzakeen, kalkulatu aurpegien mediana ere bai. Datu-marko baten aldagai bat aukeratzeko **$** sinboloa erabiltzen da.

`@hint`
1. komandoen aldagaiak parentesisen artean jarri
2. etzazu ahaztu datu-markoan aldagaia aukeratzeko **$** erabileaz

`@pre_exercise_code`
```{r}
oroimen.data <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
```

`@sample_code`
```{r}
#kalkulatu aurpegi kopuruaren batazbestekoa
____(oroimen.data$Aurpegiak)
#kalkulatu aurpegi kopuruaren mediana
______(oroimen.data$_________)
```

`@solution`
```{r}
mean(oroimen.data$Aurpegiak)
median(oroimen.data$Aurpegiak)
```

`@sct`
```{r}

```

---

## Insert exercise title here

```yaml
type: MultipleChoiceExercise
key: a8dda858bc
xp: 50
```



`@possible_answers`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sct`
```{r}

```
