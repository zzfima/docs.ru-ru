---
title: Типы исключения
description: Узнайте, как определить и использовать F# типы исключений.
ms.date: 05/16/2016
ms.openlocfilehash: b7203dc042c7207bca95cfd0372790bfe52e0226
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645571"
---
# <a name="exception-types"></a>Типы исключения

Существует две категории исключений в F#: типы исключений .NET и F# типы исключений. В этом разделе описывается определение и использование F# типы исключений.

## <a name="syntax"></a>Синтаксис

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *тип исключения* имя нового F# тип исключения, и *тип аргумента* представляет тип аргумента, могут быть предоставлены при вызова исключения этого типа. Можно указать несколько аргументов с помощью типа кортежа для *типов аргументов*.

Типичное определение F# исключение имеет следующий вид.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Исключения этого типа можно создать с помощью `raise` функции, как показано ниже.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Можно использовать F# тип исключения, непосредственно в фильтрах в `try...with` выражения, как показано в следующем примере.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Тип исключения, определенный с помощью `exception` ключевое слово в F# — это новый тип, который наследует от `System.Exception`.

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Иерархия исключений](https://msdn.microsoft.com/library/z4c5tckx.aspx)
