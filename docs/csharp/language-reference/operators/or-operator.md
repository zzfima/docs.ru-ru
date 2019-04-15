---
title: Справочник по C#. Оператор |
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312882"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор |

Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`. Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов. Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.

## <a name="remarks"></a>Примечания

Бинарный оператор `|` вычисляет оба операнда независимо от значения первого из них, в отличие от [условного оператора OR](boolean-logical-operators.md#conditional-logical-or-operator-)`||`.

Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../keywords/operator.md)) .

## <a name="example"></a>Пример

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)