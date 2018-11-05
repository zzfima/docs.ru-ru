---
title: Оператор %= (Справочник по C#)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: ab3a6a8d5cbfeb4d527ca1f9c233ddfaba3d35ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188720"
---
# <a name="-operator-c-reference"></a>Оператор %= (Справочник по C#)

Оператор присваивания остатка.

Выражение, использующее оператор `%=`, такое как  

```csharp
x %= y
```  

эквивалентно  

```csharp
x = x % y
```  

за исключением того, что `x` вычисляется только один раз.
  
[Оператор остатка](remainder-operator.md) `%` вычисляет остаток от деления двух операндов. Он поддерживается всеми числовыми типами данных.

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор остатка](remainder-operator.md) `%`, оператор присваивания остатка `%=` неявно перегружается.
  
В следующем примере иллюстрируется использование оператора `%=`.

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
