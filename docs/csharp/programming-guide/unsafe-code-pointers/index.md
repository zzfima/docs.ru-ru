---
title: Руководство по программированию в C#. Небезопасный код и указатели
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 7d7371fb29f12a766ef6b78544f82d021dd8dceb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237913"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>Небезопасный код и указатели (Руководство по программированию в C#)
Для обеспечения типобезопасности и безопасности язык C# по умолчанию не поддерживает арифметику указателей. Но ключевое слово [unsafe](../../../csharp/language-reference/keywords/unsafe.md) позволяет задать небезопасный контекст, в котором использование указателей возможно. Дополнительные сведения об указателях см. в разделе [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
> [!NOTE]
>  В общеязыковой среде выполнения (CLR) небезопасный код называется непроверяемым. Небезопасный код в C# не обязательно опасен, просто его безопасность нельзя проверить в CLR. Поэтому CLR будет выполнять небезопасный код, только если он находится в полностью доверенной сборке. Если вы используете небезопасный код, вы сами несете ответственность за возможные риски безопасности и ошибки указателей.  
  
## <a name="unsafe-code-overview"></a>Общие сведения о небезопасном коде  
 Небезопасный код имеет следующие свойства:  
  
-   Методы, типы и блоки кода можно определить как небезопасные.  
  
-   В некоторых случаях небезопасный код может увеличить скорость работы приложения, если не проверяются границы массивов.  
  
-   Небезопасный код необходим при вызове встроенных стандартных функций, требующих указателей.  
  
-   Использование небезопасного кода создает риски для стабильности и безопасности.  
  
-   Чтобы скомпилировать небезопасный код на C#, приложение нужно компилировать с помощью [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [Практическое руководство. Использование указателей для копирования массива байтов](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
