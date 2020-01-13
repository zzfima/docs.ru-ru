---
title: void. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 465aaeadca603f14432478a7e5496a9ef4589ebe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712862"
---
# <a name="void-c-reference"></a>void (справочник по C#)

При использовании в качестве типа возвращаемого значения для метода ключевое слово `void` указывает, что метод не возвращает значение.

Ключевое слово `void` не допускается в списке параметров метода. Не принимающий параметров и не возвращающий значений метод объявляется следующим образом:

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип. Дополнительные сведения см. в разделе [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md).

`void` — это псевдоним для типа <xref:System.Void?displayProperty=nameWithType> в .NET Framework.

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Ссылочные типы](reference-types.md)
- [Типы значений](value-types.md)
- [Методы](../../programming-guide/classes-and-structs/methods.md)
- [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md)
