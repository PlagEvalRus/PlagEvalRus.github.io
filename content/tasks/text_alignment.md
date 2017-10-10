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
- [Описание набора данных](#описание-набора-данных)
- [Формат ответа](#формат-ответа)
- [Базовый метод](#базовый-метод)
- [Метрики качества](#метрики-качества)
- [Оценка качества на тестовом наборе данных](#оценка-качества-на-тестовом-наборе-данных)

<!-- markdown-toc end -->


## Описание задачи
Для заданной пары текстов требуется обнаружить все заимствованные фрагменты.
Для каждой пары известен текст-источник и текст с заимствованиями (подозрительный текст).


## Данные
Информация о наборе данных, используемом в этой задаче представлена [здесь](/content/corpora/paraplag.html#использование-в-задаче-text-alignment).

## Описание набора данных

В папке `tasks` находятся файлы с заданиями,
описывающими заимствованные фрагменты.
Задания сгруппированы в архивах и разделяются по типу заимствований.

Для каждого типа заданий есть файл `pairs`.
Этот файл перечисляет все пары подозрительных текстов и источников,
которые нужно сравнить друг с другом.
Первая колонка в файле указывает на подозрительный текст
(сам файл находится в директории `susp`),
вторая колонка указывает на источник (файл находится в директории `src`).

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
$ mkdir manually-paraphrased-result
$ python text_alignment_baseline.py tasks/manually-paraphrased/pairs src susp manually-paraphrased-result
```
Пример запуска сразу для всех заданий:
```bash
$ mkdir all-results
$ python text_alignment_baseline.py tasks/pairs src susp all-results
```

## Метрики качества

Для оценки качества обнаружения заимствований используются микро-усредненные точность, полнота и др.
Подробнее прочитать про использованные метрики можно по [ссылке](http://www.uni-weimar.de/medien/webis/publications/papers/stein_2010p.pdf#page=2).
Для оценки качества во время обучения нужно использовать [скрипт](https://raw.githubusercontent.com/PlagEvalRus/text_alignment_measures/master/text_alignment_measures.py).

Пример запуска только для одного типа заданий:
```bash
$ python text_alignment_measures.py --micro -p tasks/manually-paraphrased/ -d manually-paraphrased-result/
```
где `manually-paraphrased-result` - папка, содержащая результаты обнаружения заимствованных фрагментов для заданий из папки `tasks/manually-paraphrased`.

Пример запуска сразу для всех заданий:
```bash
$ python text_alignment_measures.py --micro -p tasks/ -d all-results/
```

## Оценка качества на тестовом наборе данных
Для оценки методов на фиксированном наборе данных используется платформа
[tira](http://www.tira.io/tasks/pan/#text-alignment).
Инструкция для получения виртуальной машины и
доступа к данным размещена на [сайте](http://pan.webis.de/technology.html) (см. секцию *Evaluation as a Service*).
После установки ПО на выданной виртуальной машине и тестирования на небольшом тренировочном корпусе,
например ~pan14-text-alignment-mini-dataset~, 
необходимо запустить прогон на тестовом наборе данных, который называется ~pan17-text-alignment-test-dataset-dialogue17-russian-2017-02-22~.
После этого нужно запустить ~Evaluator~ для получения метрик качества последнего прогона.
