---
title: Рекурсивные функции. Ключевое слово rec (F#)
description: 'Узнайте, как ключевое слово «rec» F # для определения рекурсивной функции используется с ключевым словом «let».'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1f5302c125605d2186deab0bbeaf2e84cc51edc3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="recursive-functions-the-rec-keyword"></a>Рекурсивные функции. Ключевое слово rec

`rec` Ключевое слово используется совместно с `let` ключевое слово для определения рекурсивной функции.


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
Рекурсивные функции, функции, которые вызывают сами, определяются явно в языке F #. Это делает доступными идентификаторов, которая определена в области видимости функции.

Следующий код иллюстрирует рекурсивную функцию, которая вычисляет *n*Фибоначчи.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
На практике подобное приведенный выше код является лишних затрат времени процессора и памяти, так как подразумевает перерасчет ранее вычисленных значений.


Методы являются неявно рекурсивными в пределах типа; Нет необходимости для добавления `rec` ключевое слово. Привязки let в пределах классов не являются неявно рекурсивными.


## <a name="mutually-recursive-functions"></a>Взаимно рекурсивные функции
Иногда функции являются *взаимно рекурсивные*, это значит, что круг, где одна функция вызывает другую, который в свою очередь вызывает первый, с любого количества вызовов между ними. Необходимо определить такие функции в один `let` привязки с использованием `and` ключевое слово, чтобы связать их друг с другом.

В следующем примере показаны два взаимно рекурсивные функции.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>См. также
[Функции](index.md)
