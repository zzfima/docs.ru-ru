---
title: Справочник по C#. Оператор -=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333334"
---
# <a name="--operator-c-reference"></a>Справочник по C#. Оператор -=

Оператор присваивания вычитания.

## <a name="remarks"></a>Примечания

Выражение, использующее оператор присваивания `-=`, такое как

```csharp
x -= y
```

 эквивалентно

```csharp
x = x - y
```

за исключением того, что `x` вычисляется только один раз. Значение [- operator](subtraction-operator.md) зависит от типов `x` и `y` (вычитание для числовых операндов, удаление делегатов для операндов делегатов и т. д.).

Оператор `-=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [- operator](subtraction-operator.md) (см. [operator](../keywords/operator.md)).

Оператор -= также используется в C# для отмены подписки на событие. Дополнительные сведения см. в разделе [Как подписке и отмене подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
