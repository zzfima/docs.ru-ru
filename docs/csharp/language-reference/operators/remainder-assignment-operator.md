---
title: Оператор %= (Справочник по C#)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085651"
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
  
[Оператор остатка](remainder-operator.md) `%` поддерживается всеми числовыми типами и вычисляет остаток от деления своих операндов.

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор остатка](remainder-operator.md) `%`, оператор присваивания остатка `%=` неявно перегружается.
  
В следующем примере иллюстрируется использование оператора `%=`.

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
