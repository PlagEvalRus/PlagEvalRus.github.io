---
layout: page
title: Руководство по созданию размеченного текста («ЭССЕ») для автоматической оценки качества результатов поиска текстовых заимствований
ref: essays2_manual
lang: ru
---

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Содержание**

- [Введение](#Введение)
- [Методика составления текста эссе](#Методика-составления-текста-эссе)
- [Техники сокрытия заимствований](#Техники-сокрытия-заимствований)
- [Дополнительные требования](#Дополнительные-требования)

<!-- markdown-toc end -->

<br>

------------

|------------|----------------------------------------------|
| **Авторы** | Соченков И.В., Зубарев Д.В. (zubarev@isa.ru) |
| **Версия** |                                          3.0 |

------------

Введение
========

Целью работы является создание множества размеченных документов,
содержащих плагиат,
для последующей оценки качества работы методов обнаружения некорректных заимствований.
Каждый разметчик выбирает тему, по которой он составляет небольшое эссе,
содержащее плагиат из других документов.
Написанный текст должен быть создан согласно методике, описанной в следующем [разделе](#Методика-составления-текста-эссе).
В результате разметки должна получиться таблица в формате Excel,
содержащая оригинальные и заимствованные предложения, а также дополнительную информацию.
[Пример](examples/Соченков - Элвис Пресли - v2.rar) результата разметки.

Методика составления текста эссе
================================

1.  Каждое эссе составляется в отдельной папке
с фамилией автора и кратким названием темы,
например: «Петров – Методы колки дров топором».

2.  Необходимо найти документы-источники на заданную тему.
Пользоваться нужно поисковыми машинами (Google, Yandex).
Источниками могут являться статьи энциклопедий,
например, «Википедии», и любые другие данные (рефераты, курсовые, книги и т.п.).

3.  Скачать найденные документы (допускаются  форматы `HTML`, `TXT`, `RTF`, `DOC`, `DOCX`, `PDF`)
и положить их в директорию ***sources*** (см. [пример](examples/Соченков - Элвис Пресли - v2.rar)).

4.  Служебные файлы (картинки, js-, css- и проч.)
гипертекстовых страниц не следует включать в архив эссе.

5.  На основе предложений из найденных документов создать заимствованные **фрагменты текста**,
используя техники сокрытия из следующего [раздела](#Техники-сокрытия-заимствований).

6.  Заполнить очередную строку в таблице ***sources\_list.xlsx***
(см. файл ***sources\_list.xlsx*** в [примере](examples/Соченков - Элвис Пресли - v2.rar)).
Для этого необходимо:

    +  Исходное предложение (предложения) занести в таблицу в колонку (колонки)
     "*Исходное предложение*".
     *Никакие модификации (удаление переносов, «лишних» пробелов и символов)
     над исходным предложением не допускаются!*

    +  Модифицированное предложение занести в колонку *"Фрагменты текста эссе"*.
    При модификации текста нужно постараться максимально скрыть факт заимствования,
    но при этом сохранить смысл и основную суть исходного высказывания в документе-источнике.

    +  В колонку *"Типы сокрытия заимствований"* **через запятую** занести коды использованных для этого фрагмента техник сокрытия заимствований – см. следующий [раздел](#Техники-сокрытия-заимствований).

    +  Название документа, из которого взято предложение
    (в точности, как оно отображается в папке ***"sources"***)
    занести в колонку *"Имя файла документа-источника"*.

    +  Во избежание ошибок, **настоятельно** рекомендуется давать документам-источникам в папке ***"sources"*** короткие имена:
    `wiki.html`, `fiction.html`, `1.txt`, `2.html`, и т.д.


Техники сокрытия заимствований
==============================


Предложения из документов-источников необходимо подвергнуть **одной или нескольким** из нижеперечисленных операций
(код операции, который должен быть записан в колонку *"Типы сокрытия заимствований"*).
Первые 7 типов (1-7) могут использоваться совместно с несколькими типами сокрытия заимствований.

1. DEL - Удаление отдельных слов (до 20%) из исходного предложения.
2. ADD - Добавление отдельных слов (до 20%) в исходное предложение.
3. LPR - Изменение форм (изменение числа, падежа, формы и времени глагола и т.п.) отдельных слов (до 30%) исходного предложения.
4. SHF - Изменение порядка следования слов или частей предложения (оборотов, частей простого предложения в составе сложного) без значительных изменений «внутри» переставляемых частей.
5. CCT - Склейка двух или более предложений исходного текста в одно предложение.
Допускается, чтобы склеиваемые предложения шли в тексте документа-источника не подряд.
6. SEP - Разбиение исходного сложного предложения на два или более самостоятельных предложения (возможно, с изменением порядка их следования в тексте).
Разбитые предложения записываются в одну ячейку *"Фрагменты текста эссе"* и разделяются по правилам оформления предложений в русском или английском языке
(т.е., как правило, отделяются точкой в конце первого предложения).
Исходное предложение заносится в одну ячейку *"Исходное предложение"*.
7. SYN - Замена отдельных слов или отдельных терминов на синонимы (например, *«поваренная соль» – «хлорид натрия»*),
замена аббревиатур на их полные расшифровки и наоборот, раскрытие инициалов ФИО и наоборот, замена имени–отчества на инициалы и т.п.
8. HPR - Сильная переработка исходного предложения, которая является комбинацией многих (3–5 и более) типов модификации текста, приведённых выше.
Этот же тип предполагает сильное изменение исходного текста путём перифразы с использованием идиоматических выражений, сложных синонимических конструкций,
перестановку слов или частей сложного предложения и т.п. приемы, в совокупности затрудняющие определение соответствия между источником-оригиналом и изменённым текстом.
Может использоваться как отдельно (в случае сильного перифраза, когда выделить простые типы сокрытия 1–7 затруднительно),
так и совместно с типами сокрытия заимствований 1–7, если их удаётся выделить явно.


Дополнительные требования
=========================

1.  Минимальный размер эссе – ***100*** предложений.

2.  Количество документов-источников должно быть не менее 5.

3.  Из каждого документа-источника должно быть взято не менее 5% от общего числа фрагментов в эссе.

4.  Подсчёт объёма эссе ведётся по предложениям,
взятым из документа источника
(по заполненным ячейкам в колонках *"Исходное предложение"*).

5.  Минимальная длина засчитываемого фрагмента/предложения – 5 значащих слов
(предлоги, союзы, личные местоимения не учитываются!).

6.  Средняя длина предложений эссе должна быть не менее 9 слов.
(В идеале = 10,38 слова, как норма для русского языка в целом.)

7.  Предложения из источников и оригинальные предложения могут идти в произвольном порядке.

8.  Текст эссе должен быть связным,
после его прочтения должно быть ясно, какой теме он посвящён,
каковы его основные мысли.

9.  Соотношение фрагментов в эссе должно быть следующим:
    + Оригинальные фрагменты: 5–10%.
    + **CPY-фрагменты — 0% («копипаста» не допускается!)**
    + HPR-фрагменты: 20–40%.
    + Остальные фрагменты с типами сокрытия заимствований из предыдущего [раздела](#Техники-сокрытия-заимствований) – не менее 10% для каждого типа.   

10.  Не будет ошибкой, если Вы использовали более 4 техник заимствований 1–7,
но не выставили тип HPR.
Тип сокрытия заимствований HPR отдельно от остальных типов **должен использоваться только в тех случаях,
когда фрагмент перифразирован настолько сильно,
что выделить боле простые типы сокрытия 1–7 невозможно.**

11.  Оригинальные, незаимствованные, предложения (написанные самостоятельно),
должны размещаться в колонке *"Фрагменты текста эссе"*.
При этом колонки *"Имя файла документа-источника"*, *"Исходное предложение"* и *"Типы сокрытия заимствований"* **должны быть пустыми**.

12.  Оригинальные, незаимствованные,
предложения ***должны быть написаны самостоятельно*** –
не должны встречаться в других источниках,
в том числе не включённых в состав эссе.
Допускаются только случайные единичные совпадения
(как правило, не абсолютные, а лишь частичные, фрагментарные)
оригинальных незаимствованных предложений с другими предложениями в каких-либо других источниках.

13.  **Обратите внимание:** автор *эссе должен стремиться скрыть факт заимствования* с применением указанных техник.
**Чем лучше это удастся автору, тем выше оценка за эссе.**
Добавление/удаление только *одного единственного* слова (зачастую, служебного)
в подавляющем большинстве предложений (длиною более 10-15 слов)
является недостаточным (применение только типов заимствований ADD/DEL по одному слову).
Равно, как не является достаточным использование только какой-либо одной техники сокрытия заимствований из предыдущего [раздела](#Техники-сокрытия-заимствований) для значительного числа фрагментов.