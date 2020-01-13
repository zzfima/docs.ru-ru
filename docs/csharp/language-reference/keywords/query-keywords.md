---
title: Ключевые слова запроса. Справочник по C#
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 3c08c2b6ecdaa4b875f118531e7e77f7164dd784
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713161"
---
# <a name="query-keywords-c-reference"></a>Ключевые слова запроса (Справочник по C#)

В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.

## <a name="in-this-section"></a>Содержание раздела

|Предложение|Описание|
|------------|-----------------|
|[from](from-clause.md)|Задает источник данных и переменную диапазона (аналогично переменной итерации).|
|[where](where-clause.md)|Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).|
|[select](select-clause.md)|Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.|
|[group](group-clause.md)|Группирует результаты запроса по заданному значению ключа.|
|[into](into.md)|Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.|
|[orderby](orderby-clause.md)|Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.|
|[join](join-clause.md)|Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.|
|[let](let-clause.md)|Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.|
|[in](in.md)|Контекстное ключевое слово в предложении [join](join-clause.md).|
|[on](on.md)|Контекстное ключевое слово в предложении [join](join-clause.md).|
|[equals](equals.md)|Контекстное ключевое слово в предложении [join](join-clause.md).|
|[by](by.md)|Контекстное ключевое слово в предложении [group](group-clause.md).|
|[ascending](ascending.md)|Контекстное ключевое слово в предложении [orderby](orderby-clause.md).|
|[descending](descending.md)|Контекстное ключевое слово в предложении [orderby](orderby-clause.md).|

## <a name="see-also"></a>См. также

- [Ключевые слова в C#](index.md)
- [Встроенный язык запросов LINQ](../../programming-guide/concepts/linq/index.md)
- [LINQ в C#](../../linq/index.md)
- [Приступая к работе с LINQ в C#](/dotnet/csharp/programming-guide/concepts/linq/)
