---
title: Типы исключений (F#)
description: Узнайте, как определить и использовать типы исключений F#.
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858825"
---
# <a name="exception-types"></a>Типы исключения

Существует две категории исключений в языке F#: типы исключений .NET и типы исключений F#. В этом разделе описывается определение и использование типов исключений F#.

## <a name="syntax"></a>Синтаксис

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *тип исключения* имя нового типа исключения F#, и *тип аргумента* представляет тип аргумента, могут быть предоставлены при вызова исключения этого типа. Можно указать несколько аргументов с помощью типа кортежа для *типов аргументов*.

Типичное определение исключения F# выглядит следующим образом.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Исключения этого типа можно создать с помощью `raise` функции, как показано ниже.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Тип исключения F# можно использовать непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Тип исключения, определенный с помощью `exception` ключевое слово в F# — это новый тип, который наследует от `System.Exception`.

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Иерархия исключений](https://msdn.microsoft.com/library/z4c5tckx.aspx)
