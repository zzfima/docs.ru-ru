---
title: Типы исключения
description: Узнайте, как определять и использовать F# типы исключений.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630312"
---
# <a name="exception-types"></a>Типы исключения

Существует две категории исключений в F#: типы исключений .NET и F# типы исключений. В этом разделе описывается определение и использование F# типов исключений.

## <a name="syntax"></a>Синтаксис

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Примечания

В предыдущем синтаксисе *Exception-Type* — это имя нового F# типа исключения, а *аргумент-Type* представляет тип аргумента, который может быть указан при вызове исключения этого типа. Можно указать несколько аргументов с помощью типа кортежа для *типа аргумента*.

Типичное определение F# исключения напоминает следующее.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Исключение этого типа можно создать с помощью `raise` функции, как показано ниже.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Тип F# исключения можно использовать непосредственно в фильтрах в `try...with` выражении, как показано в следующем примере.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Тип исключения, определяемый с помощью `exception` ключевого слова в F# , является новым типом, который наследует от `System.Exception`.

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Иерархия исключений](https://msdn.microsoft.com/library/z4c5tckx.aspx)
