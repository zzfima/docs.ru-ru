---
title: Справочник по C#. Ключевое слово unsafe
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: ef98809eae0329c028dfb318c4a437aae4736db1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712992"
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

Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок. Пример:

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
