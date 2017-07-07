---
layout: page
title: Руководство по созданию размеченного текста (эссе) с дословными и перефразированными заимствованиями
ref: essays1_manual
lang: ru
---

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Содержание**

- [Введение](#Введение)
- [Методика составления текста](#Методика-составления-текста)
- [Техники сокрытия заимствований](#Техники-сокрытия-заимствований)
- [Дополнительные требования](#Дополнительные-требования)

<!-- markdown-toc end -->

<br>

------------

|------------|----------------------------------------------|
| **Авторы** | Соченков И.В., Зубарев Д.В. (zubarev@isa.ru) |
| **Версия** |                                          2.3 |

------------

Введение
========

Целью работы является создание множества размеченных документов,
содержащих плагиат, для последующей оценки качества работы методов обнаружения некорректных заимствований.
Каждый разметчик выбирает тему, по которой он составляет небольшое эссе,
содержащее плагиат из других документов.
Написанный текст должен быть создан согласно методике, описанной в следующем [разделе](#Методика-составления-текста).
В результате разметки должна получиться таблица в формате Excel,
содержащая оригинальные и заимствованные предложения,
а также дополнительную информацию.
[Пример](examples/Соченков - Элвис Пресли - v1.rar) результата разметки.

Методика составления текста
===========================

1.  Каждое эссе составляется в отдельной папке с фамилией автора и кратким названием темы, например: «Петров – Методы колки дров топором».

2.  Необходимо найти документы-источники на заданную тему.
Пользоваться нужно поисковыми машинами (Google, Yandex).
Источниками могут являться статьи энциклопедий, например, «Википедии», и любые другие данные (рефераты, курсовые, книги и т.п.).

3.  Скачать найденные документы (допускаются форматы `HTML`, `TXT`, `RTF`, `DOC`, `DOCX`, `PDF`)
и положить их в директорию ***sources*** (см. [пример](examples/Соченков - Элвис Пресли - v1.rar)).

4.  На основе предложений из найденных документов создать заимствованные предложения,
используя техники сокрытия из следующего [раздела](#Техники-сокрытия-заимствований).

5.  Заполнить очередную строку в таблице ***sources\_list.xlsx*** (см. файл ***sources\_list.xlsx*** в [примере](examples/Соченков - Элвис Пресли - v1.rar)).
Для этого необходимо:

    + Оригинальное предложение занести в таблицу в колонку "оригинальное предложение".
    Никакие модификации (удаление переносов, «лишних» пробелов и символов) над «оригинальным предложением» не допускаются!

    +  Модифицированное предложение занести в колонку "заимствованное предложение".

    + В колонку "тип заимствования" занести код, использованного заимствования.
    Операции модификации и список их кодов представлен в следующем разделе.

    + Название документа, из которого взято предложение
    (в точности, как оно отображается в папке «***sources***») занести в колонку "название документа-источника".

    + Во избежание ошибок, рекомендуется давать документам-источникам в папке «***sources***» короткие имена: `wiki.html`, `lurk.html`, `1.txt`, `2.html`, и т.д.

Техники сокрытия заимствований
==============================

Предложения из найденного документа необходимо подвергнуть одной из нижеперечисленных операций
(в квадратных скобках указан код операции,
который должен быть записан в колонку "тип заимствования-1"):

1.  Простое копирование предложения \[CPY\] – без какого-либо изменения исходного текста.

2.  Небольшие изменения исходного предложения:

    +  Удаление небольшого количества слов (до 20–30%) из исходного предложения \[DEL\].

    +  Добавление небольшого количества (до 20–30%) слов в исходное предложение \[ADD\].

    +  Изменение (замена) до 30% слов исходного предложения. Также можно изменить порядок следования слов или частей предложения (оборотов, частей простого предложения в составе сложного) и, если необходимо, добавить или удалить небольшое количество слов (до 10%) \[LPR\].

    +  Склейка двух или более предложений исходного текста в одно предложение. Допускается добавление / удаление / изменение до 5–10% слов изменённого предложения \[CCT\]. Оба оригинальных предложения должны быть размещены вместе в соответствующей ячейке в колонке "оригинальное предложение" (см. [пример](examples/Соченков - Элвис Пресли - v1.rar)).

    +  Разбиение предложения исходного текста на два предложения. Допускается добавление / удаление / изменение до 5–10% слов изменённых предложений \[SSP\].

3.  Сильная переработка исходного предложения:

    +  Изменение более 30% слов исходного предложения (замена на синонимы целых групп слов). Также можно добавлять или удалять слова, переставлять фрагменты с сохранением исходного смысла \[HPR\].

Если вы не можете однозначно идентифицировать тип заимствования
(по вашему мнению, заимствованный вами фрагмент относится к нескольким типам по приведённой выше классификации),
то укажите в графе "тип заимствования-1" наиболее подходящий с вашей точки зрения тип заимствования,
а в соседней колонке "тип заимствования-2" укажите альтернативный тип.

Дополнительные требования
=========================

1.  Количество документов-источников должно быть не менее 5.

2.  Должны быть использованы ***все*** техники сокрытия, описанные в предыдущем [разделе](#Техники-сокрытия-заимствований).

3.  Минимальный размер эссе – 150 предложений.

4.  Минимальная длина засчитываемого предложения = 5 слов.

5.  Средняя длина предложений эссе должна быть не менее 9 слов.

6.  Минимальное число предложений, заимствованных из одного источника, – 4.

7.  Предложения из источников и оригинальные предложения могут идти в произвольном порядке.

8.  Текст эссе должен быть связным, после его прочтения должно быть ясно, какой теме он посвящён, каковы его основные мысли.

9.  Соотношение предложений в эссе должно быть следующим:
    +  Оригинальные предложения: 10–40%.
    +  CPY- предложения 0–10%
    +  DEL-предложения: 20–30%.
    +  ADD-предложения: 15–25%.
    +  LPR-предложения: 10–30%.
    +  CCT- предложения: 5–15%.
    +  SSP-предложения: 5–15%.
    +  HPR-предложения: 5–20%.
10.  Оригинальные, незаимствованные, предложения (написанные самостоятельно), должны размещаться в колонке "заимствованное предложение".
При этом колонки "оригинальное предложение", "название документа-источника" и "тип заимствования" должны быть пустыми.
Оригинальные, незаимствованные, предложения ***должны быть написаны самостоятельно*** – не должны встречаться в других источниках, в том числе не включённых в состав эссе.
Допускаются только случайные единичные совпадения (как правило, не абсолютные, а лишь частичные, фрагментарные) оригинальных незаимствованных предложений с другими предложениями в каких-либо других источниках.
11. Обратите внимание: добавление/удаление только одного единственного слова
    (зачастую, служебного) в подавляющем большинстве предложений (длиною более
    10-15 слов) является недостаточным для типов заимствований ADD/DEL. Для
    заимствований типа ADD/DEL требуется, как правило, добавление/удаление
    нескольких смысловых (неслужебных) слов в пределах 20–30% от кол-ва слов
    исходного предложения.