---
title: 'Estatistika deskribatzailea'
description: "Zentro joerako neurriak, sakabanatze neurriak, asimetria, eta kurtosi neurriak.\n"
free_preview: true
---

## Zenbat aurpegi gogoratzen dituzu?

```yaml
type: VideoExercise
key: bf00f8136e
xp: 50
```

`@projector_key`
54afb401586af40cf88a78656b190c08

---

## Datuak eta datu-markoak

```yaml
type: NormalExercise
key: 2bafef99a3
lang: r
xp: 100
skills: 1
```

Ikus ditzagun datuak! Normalean datuak orri kalkulo moduan (datu-markoa Rn) agertuko zaizkigu non zutabe bakoitza aldagai ezberdin bat den eta lerro bakoitza behaketa ala kasu bat. Edozein analisirik egin baino lehenago oso komenigarria da gure datuen natura ezagutzea. Adibide gisa `oroimen.data` datu-markoa erabiliko dugu non pertsona bakoitzak zenbat aurpegi gogoratzen dituen ikertu zen:

[Jenkins R, Dowsett AJ, Burton AM (2018) How many faces do people know? Proceedings of the Royal Society B 285(1888): 20181319] (https://doi.org/10.1098/rspb.2018.1319)

`@instructions`
1. `oroimen.data` datu-markoa ("data frame") kargatuta daukazu, ikus ditzazu datuak `print()` komandoa erabilita
2. "**Run Code**" erabiliz esperimentatu dezakezu kodeak daukan irteera, erantzuna daukazunean "**Submit Answer**" sakatu
3. Pista bat nahi baduzu sakatu "**Take Hint**" behean

`@hint`
`bakarrik` "**Submit Answer**" sakatu, ez duzu besterik egin behar lehengo ariketa honetan

`@pre_exercise_code`
```{r}
oroimen.data <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
#https://rmarkdown.rstudio.com/authoring_basics.html
#markdown writting basics
#https://sites.trinity.edu/osl/#open great course in cognitive psy stats
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

Jarrai dezagun `oroimen.data` datu-markoa miatzen. Badaude R komandu amankomun batzuk hau egiteko, ikas ditzagun bere posibilidadeak datubasea miaketa egiten dugun bitartean. Oharrak

1. **#** sinboloa iruzkinak ipintzeko erabiliko da (honek ez du efekturik kodean)
2. Edozein unean esperimenta daiteke kontsola lehioan eta baitere kode leioan "Run Code" klik eginez, erantzun zuzenaz seguru zaudenean "Submit Answer"-ri eman eta feedback-a itxaron.

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
`head()` and `tail()` funtzioek lehenengo eta azkenengo 6 lerroak aldagien izenburuekin ematen dizkigute besteak beste.

`@hint`
`oroimen.data` ipini behar den lekuan

`@sample_code`
```{r}
#Atera datu-markoaren lehenengo 6 behaketak
head(oroimen.data)
#Atera datu-markoaren azkenego 6 behaketak. "___" ordezkatu behar den kodearekin. 
tail(_________)
```

`@solution`
```{r}
#datuen lehenengo 6 lerroak
head(oroimen.data)
#datuen azkenengo 6 lerroak
tail(oroimen.data)
```

`@sct`
```{r}
success_msg("bai, hori da, ederki ari zara!")
```

***

```yaml
type: NormalExercise
key: 18d6469d65
xp: 35
```

`@instructions`
`names()` komandoak aldagien izenak ematen ditu eta `dim()` datubasearen dimentsioak (zenbat lerro eta zenbat zutabe)

`@hint`
idatzi `?names` kontsolan

`@sample_code`
```{r}
#Zeintsuk dira "aurpegiak" datubasearen aldagaien izenak? 
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
key: 8e60ae875d
```

`@instructions`
`class()` aginduak objetu baten kategoria zer den diosku. Aplikaiozu `mean` funtzioari eta `oroimen.data`ri ere bai

`@hint`
ze pista behar duzu? pentsatu bakarrik

`@sample_code`
```{r}
#zer objetu mota da "mean" komandoa
class(mean)
#zer da "oroimen.data"
_____(__________)
```

`@solution`
```{r}
class(mean)
class(oroimen.data)
```

`@sct`
```{r}

```

***

```yaml
type: NormalExercise
key: cd34a9d446
xp: 30
```

`@instructions`
`str()` komandoak ("structure") zenbat behaketa eta aldagaiak dauden, eta inportantegoa dena: aldagaien natura diosku.

`@hint`
Idatzi komandoa str eta parentesisen artean datubasearen izena

`@sample_code`
```{r}
#aplikatu str() "oroimen.data" datu-markoari:

```

`@solution`
```{r}
str(oroimen.data)
```

`@sct`
```{r}
success_msg("oso ondo, $ sinboloa erabiltzen da aldagaiak banaka identifikatzeko, hurrengo ariketetan ulertuko duzu hobeto")
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

## Moda eta maiztasun taula

```yaml
type: MultipleChoiceExercise
key: a8dda858bc
xp: 50
```

Ez dago agindu bakar bat R-n moda zuzenean ateratzeko, baina `table()` aginduak modaz aparte informazio gehiago ematen digu, maiztasun taula bat eraikitzen du alegia. Idatzi `table(oroimen.data$Adina)` kontsolan eta emaitza behatu. Zein da datu-markoaren adinaren moda?

`@possible_answers`
- 19
- 20
- 21
- [22]

`@hint`
`barplot(table(oroimen.data$Adina))` kontsolan idatzi eta sakatu enter moda grafikoki ikusteko.

`@pre_exercise_code`
```{r}
oroimen.data <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
```

`@sct`
```{r}
msg1 <- "ez, ez da hori"
msg2 <- "hum, ez, pentsatu"
msg3 <- "ez da zuzena!"
msg4 <- "halaxe da, bai!"
ex() %>% check_mc(correct = 4,
                  feedback_msgs = c(msg1, msg2, msg3,msg4))



#https://www.r-project.org/conferences/useR-2015/presentations/245.pdf
#msg1 = "ez, ez da hori"
#msg2 = "oker zaude"
#msg3 = "ez da zuzena"
#msg4 = "bai!"

#test_mc(correct = 4, feedback_msgs = c(msg1,msg2,msg3,msg4))
#test_mc() can no longer be used in SCTs. Use its check equivalent instead.


# Final message the student will see upon completing the exercise
success_msg("bai, halan da, gehien errepikatzen den adina 22 urtetakoa izan da, 9 pertsonak adin hori dauka alegia")
```

---

## Objetuak esleitzen

```yaml
type: NormalExercise
key: b19cc38917
xp: 100
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Sakabatze neurriak

```yaml
type: VideoExercise
key: b93fbd3a14
xp: 50
```

`@projector_key`
48a6331fb2fed2d25a6c02e5dbe68212

---

## Ibiltartea

```yaml
type: NormalExercise
key: 08a53e795f
xp: 100
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Bariantza eta desbiderapen tipikoa

```yaml
type: NormalExercise
key: c7d5e04d6e
xp: 100
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Errore tipikoa

```yaml
type: NormalExercise
key: 66123ccc84
xp: 100
```

The standard error (SE) of a statistic (usually an estimate of a parameter) is the standard deviation of its sampling distribution[1] or an estimate of that standard deviation. If the parameter or the statistic is the mean, it is called the standard error of the mean (SEM). The standard error is just the standard deviation divided by the square root of the sample size.

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}
oroimen.data <- read.csv(url("https://assets.datacamp.com/production/repositories/4527/datasets/748592c9843be0a0c488e28c86dab3691814e629/aurpegiak.csv"))
```

`@sample_code`
```{r}

```

`@solution`
```{r}
sd(oroimen.data$Aurpegiak)/sqrt(length(x))
```

`@sct`
```{r}

```

---

## Histograma

```yaml
type: NormalExercise
key: 4657c518f0
xp: 100
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Zorroztasuna (asimetria) eta kurtosia

```yaml
type: NormalExercise
key: ee1903709b
xp: 100
```

Intuitively, the excess kurtosis describes the tail shape of the data distribution. The normal distribution has zero excess kurtosis and thus the standard tail shape. It is said to be mesokurtic. Negative excess kurtosis would indicate a thin-tailed data distribution, and is said to be platykurtic. Positive excess kurtosis would indicate a fat-tailed distribution, and is said to be leptokurtic. Kurtosis is a measure of the peakedness of a probability/frequency distribution



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}
#https://www.r-bloggers.com/measures-of-skewness-and-kurtosis/
#http://www.r-tutor.com/elementary-statistics/numerical-measures/kurtosis
```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```
