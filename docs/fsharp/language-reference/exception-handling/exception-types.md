---
title: Типы исключений (F#)
description: 'Узнайте, как определить и использовать типы исключений F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6aaa5cd1b94f829b98d5aed5dcf6e30472a8b751
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="exception-types"></a>Типы исключения

Существует две категории исключений в языке F #: типы исключений .NET и типы исключений F #. В этом разделе описывается определение и использование типов исключений F #.


## <a name="syntax"></a>Синтаксис

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Примечания
В предыдущем синтаксисе *тип исключения* имя нового типа исключения F #, и *тип аргумента* представляет тип аргумента, который может быть задан после вызова исключения этого типа. Можно указать несколько аргументов с помощью типа кортежа для *тип аргумента*.

Типичное определение исключения F # выглядит следующим образом.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Исключение этого типа можно создавать с помощью `raise` следующим образом.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Тип исключения F # можно использовать непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Тип исключения, определяемый с `exception` ключевое слово в языке F # — это новый тип, который наследует от `System.Exception`.


## <a name="see-also"></a>См. также
[Обработка исключений](index.md)

[Исключения: функция `raise`](the-raise-function.md)

[Иерархия исключений](https://msdn.microsoft.com/library/z4c5tckx.aspx)
