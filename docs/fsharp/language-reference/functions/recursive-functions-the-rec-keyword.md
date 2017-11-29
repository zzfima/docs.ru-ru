---
title: "Рекурсивные функции. Ключевое слово rec (F#)"
description: "Узнайте, как ключевое слово «rec» F # для определения рекурсивной функции используется с ключевым словом «let»."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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

Следующий код иллюстрирует рекурсивную функцию, которая вычисляет  *n* Фибоначчи.

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
