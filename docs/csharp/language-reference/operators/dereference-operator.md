---
title: Оператор -&gt; (справочник по C#)
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 178724ede105d809bd812461121a38d5a0e90517
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144134"
---
# <a name="-gt-operator-c-reference"></a>Оператор -&gt; (справочник по C#)

Оператор доступа `->` к элементу с использованием указателя объединяет косвенное обращение к указателю и доступ к элементу.

Если `x` — это указатель типа `T*`, `y` — доступный элемент `T`, выражение формы будет

```csharp
x->y
```

эквивалентно

```csharp
(*x).y
```

Для оператора `->` требуется [небезопасный](../keywords/unsafe.md) контекст.

Дополнительные сведения см. в [практическом руководстве по получению доступа к элементу с использованием указателя](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Оператор `->` перегрузить нельзя.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе о [получении доступа к элементу](~/_csharplang/spec/unsafe-code.md#pointer-member-access) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)
