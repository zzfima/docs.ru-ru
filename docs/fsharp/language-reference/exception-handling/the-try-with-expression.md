---
title: Исключения. Выражение try…with
description: Узнайте, F# как использовать оператор "try... With ' выражение для обработки исключений.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630246"
---
# <a name="exceptions-the-trywith-expression"></a>Исключения. Выражение try…with

В этом разделе описывается `try...with` выражение, которое используется для обработки исключений в F# языке.

## <a name="syntax"></a>Синтаксис

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>Примечания

Выражение используется для управления исключениями в F# `try...with` Он аналогичен `try...catch` оператору в C#. В приведенном выше синтаксисе код в *expression1* может вызвать исключение. `try...with` Выражение возвращает значение. Если исключение не создается, выражение целиком возвращает значение *expression1*. При возникновении исключения каждый *шаблон* сравнивается, в свою очередь, с исключением, а для первого совпадающего шаблона соответствующее *выражение*, известное как *обработчик исключений*для этой ветви, выполняется, а общее выражение Возвращает значение выражения в этом обработчике исключений. Если шаблон не соответствует, исключение распространяет стек вызовов до тех пор, пока не будет найден соответствующий обработчик. Типы значений, возвращаемых каждым выражением в обработчиках исключений, должны соответствовать типу, возвращаемому из выражения в `try` блоке.

Как правило, возникновение ошибки также означает, что нет допустимого значения, которое может быть возвращено из выражений в каждом обработчике исключений. Часто шаблоном является то, что тип выражения должен быть типом параметра. Этот шаблон показан в следующем примере кода.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Исключения могут быть исключениями .NET, или они могут F# быть исключениями. Исключения можно определить F# с помощью `exception` ключевого слова.

Для фильтрации по типу исключения и другим условиям можно использовать разнообразные шаблоны. параметры приведены в следующей таблице.

|Шаблон|Описание|
|-------|-----------|
|:? *тип исключения*|Соответствует указанному типу исключения .NET.|
|:? *тип Exception —* *идентификатор*|Соответствует указанному типу исключения .NET, но присваивает исключению именованное значение.|
|*имя исключения* (*аргументы*)|Соответствует типу F# исключения и привязывает аргументы.|
|*identifier*|Соответствует любому исключению и привязывает имя к объекту исключения. Эквивалентно **:? System. Exception в**качестве_идентификатора_|
|*идентификатор* при *условии*|Соответствует любому исключению, если условие истинно.|

## <a name="examples"></a>Примеры

В следующих примерах кода показано использование различных шаблонов обработчиков исключений.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> Конструкция представляет собой отдельное выражение `try...finally` из выражения. `try...with` Поэтому, если в коде требуется `with` блок `finally` и блок, необходимо вложить два выражения.

> [!NOTE]
> Можно использовать `try...with` в асинхронных рабочих процессах и других вычислительных выражениях. в этом случае используется `try...with` настроенная версия выражения. Дополнительные сведения см. в разделе [асинхронные рабочие процессы](../asynchronous-workflows.md)и [вычислительные выражения](../computation-expressions.md).

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Типы исключения](exception-types.md)
- [Исключения. `try...finally` Выражение](the-try-finally-expression.md)
