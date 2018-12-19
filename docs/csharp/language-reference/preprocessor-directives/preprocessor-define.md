---
title: '#Справочник по C#. Директива #define'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 7be2a2d00e96b4b734e1a68f6dc63180bcbe5e82
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244977"
---
# <a name="define-c-reference"></a>#define (Справочник по C#)
`#define` позволяет определить символ. При использовании символа в качестве выражения, которое передается директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), выражение будет иметь значение `true`, как показано в следующем примере:  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Директиву `#define` нельзя использовать для объявления значений констант, как это обычно делается в C и C++. Для определения констант в C# следует использовать статические элементы класса или структуры. При наличии нескольких констант имеет смысл создать для них отдельный класс "Constants".  
  
 Символы можно использовать для указания условий компиляции. Для проверки символов можно использовать директивы [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md). Для условной компиляции также можно использовать <xref:System.Diagnostics.ConditionalAttribute>.  
  
 Можно определить символ, но нельзя назначить символу значение. Директива `#define` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами препроцессора.  
  
 Также символ можно определить с помощью параметра компилятора [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md). Для отмены определения символа служит директива [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Символ, определенный с помощью `-define` или `#define`, не конфликтует с одноименной переменной. Имя переменной не должно передаваться директиве препроцессора, а символ может вычисляться только директивой препроцессора.  
  
 Область символа, которая была создана с помощью директивы `#define`, — это файл, в котором был определен символ.  
  
 Как показано в следующем примере, необходимо поместить директивы `#define` в верхнюю часть файла.  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Пример отмены определения символа см. в разделе [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [const](../../../csharp/language-reference/keywords/const.md)  
- [Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
- [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
- [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
