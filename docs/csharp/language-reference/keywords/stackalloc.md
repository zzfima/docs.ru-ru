---
title: Справочник по C#. Ключевое слово stackalloc
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: c72daa58d2fceb05d9cc9c388a9d2e5dbe062796
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422441"
---
# <a name="stackalloc-c-reference"></a>stackalloc (Справочник по C#)

Ключевое слово `stackalloc` используется для выделения блока памяти стеку.

```csharp
Span<int> block = stackalloc int[100];
```

Назначение выделенного блока <xref:System.Span%601?displayName=nameWithType> вместо `int*` позволяет выделять память стеку в безопасном блоке. Контекст `unsafe` не требуется.

## <a name="remarks"></a>Примечания

Это ключевое слово допустимо только в инициализаторах локальных переменных. Следующий код вызывает ошибки компилятора.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

Начиная с версии C# 7.3 для массивов `stackalloc` можно использовать синтаксис инициализатора массива. Во всех следующих примерах объявляется массив с тремя элементами, имеющими целочисленные значения `1`, `2` и `3`. Вторая инициализация назначает память <xref:System.ReadOnlySpan%601>, указывая на то, что память не может быть изменена.

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

Когда используются типы указателей, для `stackalloc` требуется [небезопасный](unsafe.md) контекст. Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).

`stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.

## <a name="examples"></a>Примеры

Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи. Каждое из них представляет собой сумму двух предыдущих чисел. В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку. Адрес блока хранится в `Span` `fib`. Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](fixed-statement.md)). Время существования блока памяти ограничивается временем существования метода, который его определяет. Освободить эту память прежде, чем метод выдаст результат, невозможно.

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

В приведенном ниже примере массив целых чисел `stackalloc` инициализируется с использованием битовой маски, задающей один бит в каждом элементе. Таким образом в нем демонстрируется использование нового синтаксиса инициализатора, доступного начиная с версии C# 7.3.

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Безопасность

По возможности следует использовать <xref:System.Span%601> или <xref:System.ReadOnlySpan%601>, так как неуправляемый код менее безопасен, чем безопасные аналоги. Но даже при работе с указателями при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера. Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.

## <a name="c-language-specification"></a>Спецификация языка C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md)
