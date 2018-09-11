---
title: Рекурсивные функции. Ключевое слово rec (F#)
description: 'Узнайте, как ключевое слово «rec» F # используется с ключевым словом «let» для определения рекурсивной функции.'
ms.date: 05/16/2016
ms.openlocfilehash: 5aab6ed8ab0fc3c0f0bcfc93c3ce6518ec53254f
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44336515"
---
# <a name="recursive-functions-the-rec-keyword"></a>Рекурсивные функции. Ключевое слово rec

`rec` Ключевое слово используется вместе с `let` ключевое слово для определения рекурсивной функции.

## <a name="syntax"></a>Синтаксис

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>Примечания

Рекурсивные функции, функции, которые вызывают сами себя, явным образом определяются на языке F #. Это делает доступным идентификатор, который определяется в области видимости функции.

Следующий код иллюстрирует рекурсивную функцию, которая вычисляет *n*<sup>th</sup> число Фибоначчи.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
На практике, приведенный выше код неэффективен времени процессора и памяти, так как подразумевает перерасчет ранее вычисленных значений.

Методы являются неявно рекурсивными в пределах типа; Нет необходимости, чтобы добавить `rec` ключевое слово. Привязки let в классах не являются неявно рекурсивными.

## <a name="mutually-recursive-functions"></a>Взаимно рекурсивные функции

Иногда функции являются *взаимно рекурсивные*, это значит, что круг, где одна функция вызывает другую, которая в свою очередь вызывает первый, с любым количеством вызовов между ними. Такие функции должны определять вместе в одном `let` привязка, с помощью `and` ключевое слово, чтобы связать их друг с другом.

В следующем примере показано два взаимно рекурсивные функции.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>См. также

- [Функции](index.md)
