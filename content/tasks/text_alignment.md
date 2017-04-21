---
layout: page
title: Определение заимствованных фрагментов
ref: text_alignment
lang: ru
---
<!-- ### Содержание -->
<!-- [На главную](index.html)    -->
<!-- [Данные для обучения](data.html)   -->
<!-- [Источники](source.html)   -->
<!-- [Текст](text_element.html)   -->
<!-- [Соревнования](index_data.html)   -->
<!-- [Задания](index_task.html) -->

### Данные
Информация по данным используемым в этой задаче представлена [здесь](/content/corpora/paraplag.html).

### Инструкция по работе с данными

В папке `tasks` находятся файлы с заданиями,
описывающими заимствованные фрагменты.
Задания сгруппированы в архивах и разделяются по типу заимствований.

Для каждого типа заданий есть файл `pairs`.
Этот файл перечисляет все пары подозрительных документов и источников,
которые нужно сравнить друг с другом.
Первая колонка в файле указывает на подозрительный документ
(сам файл находится в директории `susp`),
вторая колонка указывает на источник (файл находится в директории `src`).

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
В источнике `ABC.txt `текст,
который был заимствован, начинается с 100-ого символа и имеет длину 150 символов.

В качестве базового метода (`baseline`) можно использовать [программу](http://www.uni-weimar.de/medien/webis/events/pan-12/pan12-code/pan12-text-alignment-baseline.py)

Пример запуска:
```bash
$ python pan12-text-alignment-baseline.py tasks/manually-paraphrased/pairs src susp manually-paraphrased-result
```

С результатами базового метода можно сравнивать результаты своих методов.
Для оценки качества обнаружения заимствований будут использоваться микро-усредненные точность, полнота и др.
Подробнее прочитать про использованные метрики можно по [ссылке](http://www.uni-weimar.de/medien/webis/publications/papers/stein_2010p.pdf#page=2)
Для оценки качества во время обучения можно использовать [скрипт](http://www.uni-weimar.de/medien/webis/events/pan-09/pan09-code/pan09-plagiarism-detection-performance-measures.py)

Пример запуска:
```bash
$ python pan09-plagiarism-detection-performance-measures.py -p tasks/manually-paraphrased/-d manually-paraphrased-result/
```

<!-- На этапе оценки прогонов участники должны будут сдать свои программы (скрипты), которые -->
<!-- будут автоматически запускаться на платформе TIRA на закрытом множестве контрольных -->
<!-- заданий. Программы будут запускаться следующим образом: -->
<!-- ``` -->
<!-- mySoftware-i path/to/corpus-o path/to/output/directory -->
<!-- ``` -->

<!-- На платформе TIRA участникам будет выделена персональная виртуальная машина, с одной из следующих ОС: Windows 7 или Ubuntu 12.04. Можно использовать любой язык программирования. Доступ к виртуальной машине будет организован через `ssh` или `rdp`. Детальная информация о работе с ВМ <http://pan.webis.de/clef14/pan14-web/pan14-virtual-machine-user-guide.pdf> -->
