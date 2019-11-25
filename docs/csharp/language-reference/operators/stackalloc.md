---
title: Справочник по C#. Оператор stackalloc
ms.custom: seodec18
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 82fc1649bac66c0e934db13c50390b977432c34c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036145"
---
# <a name="stackalloc-operator-c-reference"></a>Оператор stackalloc (Справочник по C#)

Оператор `stackalloc` выделяет блок памяти в стеке. Выделенный в стеке блок памяти, который создает этот метод, автоматически удаляется по завершении выполнения метода. Вы не можете явным образом освободить память, выделенную оператором `stackalloc`. Выделенный в стеке блок памяти не подвергается [сборке мусора](../../../standard/garbage-collection/index.md), поэтому его не нужно закреплять с помощью [инструкции `fixed`](../keywords/fixed-statement.md).

В выражении `stackalloc T[E]` элемент `T` должен быть [неуправляемым типом](../builtin-types/unmanaged-types.md), а элемент `E` — выражением типа `int`.

Результат выполнения оператора `stackalloc` вы можете присвоить переменной любого из следующих типов:

- Начиная с версии C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> или <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, как показано в следующем примере:

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  Нет необходимости использовать [небезопасный](../keywords/unsafe.md) контекст при назначении выделенного в стеке блока памяти переменной <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.

  При работе с такими типами вы можете использовать выражение `stackalloc` в [условном](conditional-operator.md) выражении или выражении присваивания, как показано в следующем примере:

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  Начиная с версии C# 8.0, можно использовать выражение `stackalloc` внутри других выражений, если разрешена переменная <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>, как показано в следующем примере:

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > Мы рекомендуем везде, где это возможно, использовать для работы с выделенной в стеке памятью типы <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>.

- [Тип указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md), как показано в следующем примере.

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  Как демонстрирует пример выше, при работе с типами указателей необходимо использовать контекст `unsafe`.

  В случае типов указателей можно использовать выражение `stackalloc` только в объявлении локальной переменной для инициализации переменной.

Содержимое только что выделенной памяти не определено. Начиная с версии C# 7.3, вы можете использовать синтаксис инициализатора массива, чтобы определить содержимое для только что выделенной памяти. В следующем примере показано несколько способов сделать это:

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a>Безопасность

При использовании `stackalloc` в среде CLR автоматически включается контроль переполнения буфера. Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) (Выделение памяти в стеке) из [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Операторы, связанные с указателем](pointer-related-operators.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Типы, связанные с памятью и диапазонами](../../../standard/memory-and-spans/index.md)
