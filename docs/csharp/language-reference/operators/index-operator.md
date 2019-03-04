---
title: Справочник по C#. Оператор []
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835594"
---
# <a name="-operator-c-reference"></a>Оператор [].Справочник по C#

Квадратные скобки, `[]`, обычно используются для доступа к элементам массива, индексатора или указателя.

Дополнительные сведения см. в [практическом руководстве по доступу к элементу массива с использованием указателя](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).

Кроме того, с помощью квадратных скобок можно указывать [атрибуты](../../programming-guide/concepts/attributes/index.md).

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a>Доступ к массиву

В приведенном ниже примере показано, как получить доступ к элементам массива.

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

Если индекс массива выходит за границы соответствующего измерения массива, возникает исключение <xref:System.IndexOutOfRangeException>.

Как показано в предыдущем примере, квадратные скобки также используются в объявлении типа массива и для создания экземпляров массива.

Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).

## <a name="indexer-access"></a>Доступ к индексатору

В приведенном ниже примере используется тип .NET <xref:System.Collections.Generic.Dictionary%602> для демонстрации доступа к индексатору.

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

Индексаторы позволяют индексировать экземпляры определяемого пользователем типа аналогично индексации массива. В отличие от индексов массива, которые должны быть целым числом, аргументы индексатора могут быть объявлены любым типом.

Дополнительные сведения см. в [руководстве по работе с индексаторами](../../programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Доступ к элементам `[]` не считается перегружаемым оператором. Используйте [индексаторы](../../programming-guide/indexers/index.md) для поддержки индексирования с помощью определяемых пользователем типов.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделах [Доступ к элементам](~/_csharplang/spec/expressions.md#element-access) и [Доступ к элементу указателя](~/_csharplang/spec/unsafe-code.md#pointer-element-access) [спецификации C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Массивы](../../programming-guide/arrays/index.md)
- [Индексаторы](../../programming-guide/indexers/index.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Атрибуты](../../programming-guide/concepts/attributes/index.md)
- [Операторы ?. и ?[]](null-conditional-operators.md)