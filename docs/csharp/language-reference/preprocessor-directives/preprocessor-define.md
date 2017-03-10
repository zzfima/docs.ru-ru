---
title: "#define (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#define - директива [C#]"
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# #define (Справочник по C#)
`#define` позволяет определить символ.  При использовании символа в качестве выражения, которое передается директиве [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), выражение будет иметь значение `true` как показано в следующем примере:  
  
 `#`  `define`   `DEBUG`  
  
## Заметки  
  
> [!NOTE]
>  Директиву `#define` нельзя использовать для объявления значений констант, как это делается в C и C\+\+.  Для определения констант в C\# следует использовать статические элементы класса или структуры.  При наличии нескольких констант имеет смысл создать для них отдельный класс "Constants".  
  
 Символы можно использовать для указания условий компиляции.  Для проверки символов можно использовать директивы [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).  Для условной компиляции также можно использовать атрибут `conditional`.  
  
 Можно определить символ, но нельзя назначить символу значение.  Директива `#define` должна присутствовать в файле до использования каких\-либо инструкций, не являющихся также директивами препроцессора.  
  
 Также можно определить символ с помощью параметра компилятора [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).  Для отмены определения символа служит директива [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Символ, определенный с помощью `/define` или `#define`, не конфликтует с одноименной переменной.  Имя переменной не должно передаваться директиве предварительной обработки, а символ может вычисляться только директивой предварительной обработки.  
  
 Область символа, созданная с помощью директивы `#define`, — это файл, в котором символ был определен.  
  
 Как показано в следующем примере, необходимо размещать директивы `#define` вверху файла.  
  
```c#  
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
  
 Пример отмены определения символа см. в разделе [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [How to: Compile Conditionally with Trace and Debug](../Topic/How%20to:%20Compile%20Conditionally%20with%20Trace%20and%20Debug.md)   
 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)   
 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)