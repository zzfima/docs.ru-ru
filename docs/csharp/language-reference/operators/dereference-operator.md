---
title: Оператор -> — справочник по C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: be74f02a85aa05cdab32768ed38222fc4d9289b1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255371"
---
# <a name="--operator-c-reference"></a>Оператор -> (Справочник по C#)

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
