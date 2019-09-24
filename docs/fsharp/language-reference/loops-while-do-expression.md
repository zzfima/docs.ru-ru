---
title: 'Циклы: выражение while...do'
description: См. раздел while... выражение do используется для выполнения итеративного выполнения (циклов), пока заданное условие теста имеет значение true.
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216635"
---
# <a name="loops-whiledo-expression"></a>Циклы: выражение while...do

`while...do` Выражение используется для выполнения итеративного выполнения (цикла), пока заданное условие теста имеет значение true.

## <a name="syntax"></a>Синтаксис

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Примечания

*Тестовое выражение* вычисляется; Если это так ,товыполняетсявыражениеbody,атестовоевыражениесновавычисляется`true`. *Выражение текста* должно иметь тип `unit`. Если тестовое выражение имеет `false`значение, итерация завершается.

В следующем примере показано использование `while...do` выражения.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Выходные данные предыдущего кода — это поток случайных чисел от 1 до 20, последний из которых равен 10.

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> Можно использовать `while...do` в выражениях последовательности и других вычислительных выражениях. в этом случае используется настроенная `while...do` версия выражения. Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие процессы](asynchronous-workflows.md)и [вычислительные выражения](computation-expressions.md).

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Бираются `for...in`Выражение](loops-for-in-expression.md)
- [Бираются `for...to`Выражение](loops-for-to-expression.md)
