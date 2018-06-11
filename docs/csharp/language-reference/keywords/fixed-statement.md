---
title: Оператор fixed (Справочник по C#)
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 28c8e9bd078e07a185f541214aa5b5ff79018ff5
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "34826998"
---
# <a name="fixed-statement-c-reference"></a>Оператор fixed (Справочник по C#)

Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную. Оператор `fixed` допускается только в [небезопасном](unsafe.md) контексте. `fixed` также можно использовать для создания [буферов фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора. Указатели на перемещаемые управляемые переменные полезны только в контексте `fixed`. Без контекста `fixed` при сборке мусора эти переменные могут переноситься непредсказуемым образом. Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной. В приведенном ниже примере демонстрируется использование переменных адресов, массивов и строк. Дополнительные сведения о буферах фиксированного размера см. в разделе [Буферы фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

Начиная с C# 7.3, оператор `fixed` работает с дополнительными типами, помимо массивов, строк, буферов фиксированного размера и неуправляемых переменных. Любой тип, реализующий метод `GetPinnableReference`, можно зафиксировать. `GetPinnableReference` должен преобразовывать переменную `ref` в неуправляемый тип. Дополнительные сведения см. в статье о [типах указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md). Типы .NET <xref:System.Span%601?displayProperty=nameWithType> и <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, представленные в .NET Core 2.0, используют этот шаблон и могут быть зафиксированы. Это показано в следующем примере:

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

При создании типов, которые должны участвовать в этом шаблоне, перейдите по ссылке <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> для примера реализации шаблона.

В одном операторе можно инициализировать несколько указателей одного типа.

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора. Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`. Переменные, объявленные в операторе `fixed`, относятся к этому оператору, что упрощает выполнение следующего выражения.

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

Указатели, инициализированные в операторах `fixed`, являются переменными только для чтения. Чтобы изменить значение указателя, необходимо объявить переменную второго указателя и изменить ее. Переменную, объявленную в операторе `fixed`, изменить невозможно.

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


В небезопасном режиме вы можете выделить память в стеке, где сборка мусора не производится и, соответственно, закрепление не требуется. Дополнительные сведения см. в разделе [stackalloc](stackalloc.md).

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a>Спецификация языка C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

 [Справочник по C#](../index.md)  
 [Руководство по программированию на C#](../../programming-guide/index.md)  
 [Ключевые слова в C#](index.md)  
 [unsafe](unsafe.md)  
 [Буферы фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
