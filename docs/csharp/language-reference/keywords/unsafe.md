---
title: Справочник по C#. Ключевое слово unsafe
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: aa22eac9d4ae06753bbed1fd5733eddeddd81a46
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422271"
---
# <a name="unsafe-c-reference"></a>unsafe (Справочник по C#)

Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для выполнения любых операций с применением указателей. Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).

В объявлении типа или члена типа можно использовать модификатор `unsafe`. Все текстовое пространство типа или члена типа считается небезопасным контекстом. Например, следующий метод объявлен с модификатором `unsafe`:

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

Область небезопасного контекста простирается от списка параметров до конца метода, поэтому в списке параметров можно также использовать указатели:

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок. Например:

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

Чтобы скомпилировать небезопасный код, необходимо указать параметр компилятора [`-unsafe`](../compiler-options/unsafe-compiler-option.md). Небезопасный код не проверяется средой CLR.

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Небезопасный код](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Оператор fixed](fixed-statement.md)
- [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md)
- [Буферы фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
