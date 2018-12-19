---
title: '#undef. Справочник по C#'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 5a3658c4e6bb32158e6f81c3ac5014fbedba0713
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235773"
---
# <a name="undef-c-reference"></a>#undef (Справочник по C#)
`#undef` позволяет отменить определение символа таким образом, чтобы при использовании этого символа в качестве выражения в директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) возвращалось значение `false`.  
  
 Символ можно определить с помощью директивы [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) или параметра компилятора [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md). Директива `#undef` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами.  
  
## <a name="example"></a>Пример  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

**DEBUG не определено**

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
