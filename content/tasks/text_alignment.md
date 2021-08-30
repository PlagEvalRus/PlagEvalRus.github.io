---
layout: page
title: Определение заимствованных фрагментов (Text alignment)
ref: text_alignment
lang: ru
---
<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Содержание**

- [Описание задачи](#описание-задачи)
- [Данные](#данные)
- [Формат ответа](#формат-ответа)
- [Базовый метод](#базовый-метод)
- [Метрики качества](#метрики-качества)
- [Оценка качества на тестовом наборе данных](#оценка-качества-на-тестовом-наборе-данных)

<!-- markdown-toc end -->


## Описание задачи
Для заданной пары текстов требуется обнаружить все заимствованные фрагменты.
Для каждой пары известен текст-источник и текст с заимствованиями (подозрительный текст).


## Данные
Информация о наборе данных, используемом в этой задаче представлена [здесь](/content/corpora/paraplag_v2.html#использование-в-задаче-text-alignment).

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

## Базовый метод
В качестве базового метода (`baseline`) используется [программа](https://raw.githubusercontent.com/PlagEvalRus/text_alignment_baseline/master/text_alignment_baseline.py).

Пример запуска только для одного типа заданий:
```bash
$ mkdir /tmp/result
$ cd paraplag_v2/cross/essay1/text_alignment/test
$ python /path/to/text_alignment_baseline.py meta/pairs src susp /tmp/result
```

## Метрики качества

Для оценки качества обнаружения заимствований используются микро-усредненные точность, полнота и F1.
Подробнее прочитать про использованные метрики можно по [ссылке](http://www.uni-weimar.de/medien/webis/publications/papers/stein_2010p.pdf#page=2).
Для оценки качества нужно использовать [скрипт](https://raw.githubusercontent.com/PlagEvalRus/text_alignment_measures/master/text_alignment_measures.py).

Пример запуска:
```bash
$ python text_alignment_measures.py --micro -p paraplag_v2/cross/essay1/text_alignment/test/meta -d result/
```
где `result` - папка, содержащая результаты обнаружения заимствованных фрагментов для заданий из папки `paraplag_v2/cross/essay1/text_alignment/test/susp`.

## Оценка качества на закрытом наборе данных
Для оценки методов на закрытом наборе данных используется платформа
[tira](http://www.tira.io/tasks/pan/#text-alignment).
Инструкция для получения виртуальной машины и
доступа к данным размещена на [сайте](http://pan.webis.de/technology.html) (см. секцию *Evaluation as a Service*).
После установки ПО на выданной виртуальной машине и тестирования на небольшом тренировочном корпусе,
например `pan14-text-alignment-mini-dataset`, 
необходимо запустить прогон на тестовом наборе данных, который называется `pan17-text-alignment-test-dataset-dialogue17-russian-2017-02-22`.
После этого нужно запустить `Evaluator` для получения метрик качества последнего прогона.
