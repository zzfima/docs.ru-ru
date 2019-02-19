---
title: '! Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303716"
---
# <a name="-operator-c-reference"></a>! operator (Справочник по C#)

Оператор логического отрицания (`!`) представляет собой унарный оператор, который вычисляет логическое отрицание операнда [bool](../keywords/bool.md). То есть он создает `true`, если операнд является `false`, и `false`, если операнд — `true`.

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `!`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор логического отрицания](~/_csharplang/spec/expressions.md#logical-negation-operator) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)