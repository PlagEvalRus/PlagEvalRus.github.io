---
layout: page
title: Поиск заимствований
ref: plag_detection
lang: ru
---

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [Описание задачи](#описание-задачи)
- [Данные](#данные)
- [Формат ответа](#формат-ответа)
- [Метрики качества](#метрики-качества)

<!-- markdown-toc end -->



## Описание задачи
Для заданного текста требуется обнаружить все заимствованные фрагменты из заранее зафиксированной коллекции источников.
Решение задачи предполагает индексацию коллекции источников, которая содержит около 6 млн. документов.
Эта задача может быть разбита на две подзадачи:
[обнаружение источников заимствований (source retrieval)](source_retrieval.html) и [определение заимствованных фрагментов (text alignment)](text_alignment.html).

## Данные 
Информация о наборе данных, используемом в этой задаче представлена [здесь](/content/corpora/paraplag_v2.html#использование-для-оценки-метода-выявления-заимствований).

## Формат ответа

 Программа обнаружения заимствований должна сгенерировать XML-файл `suspicious-documentXYZ-source-documentABC.xml`,
 который содержит метаинформацию об обнаруженных заимствованиях.

Пример:
```xml
<document reference="XYZ.txt">
<feature
 name="detected-plagiarism"
 this_offset="5"
 this_length="200"
 source_reference="ABC.txt"
 source_offset="100"
 source_length="150"
/>
<feature ... />
...
</document>
```

В примере выше заимствованный текст в документе `XYZ.txt` начинается с 5-ого символа и имеет длину 200 символов.
В источнике `ABC.txt` текст,
который был заимствован, начинается с 100-ого символа и имеет длину 150 символов.

## Метрики качества

Для оценки качества обнаружения заимствований используются микро-усредненные точность, полнота и F1.
Подробнее прочитать про использованные метрики можно по [ссылке](http://www.uni-weimar.de/medien/webis/publications/papers/stein_2010p.pdf#page=2).
Для оценки качества нужно использовать [скрипт](https://raw.githubusercontent.com/PlagEvalRus/text_alignment_measures/master/text_alignment_measures.py).

Пример запуска:
```bash
$ python text_alignment_measures.py --micro -p paraplag_v2/cross/essay1/text_alignment/test/meta -d result/
```
где `result` - папка, содержащая результаты обнаружения заимствованных фрагментов для заданий из папки `paraplag_v2/cross/essay1/text_alignment/test/susp`.
