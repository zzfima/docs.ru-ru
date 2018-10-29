---
title: void (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 223db893dd42181c234d9a07c1a1c00af26f0c30
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261593"
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

Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип. Дополнительные сведения см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).

`void` — это псевдоним для типа <xref:System.Void?displayProperty=nameWithType> в .NET Framework.

## <a name="c-language-specification"></a>Спецификация языка C#
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)  
- [Типы значений](../../../csharp/language-reference/keywords/value-types.md)  
- [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
