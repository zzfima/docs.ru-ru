---
title: "#if (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#if"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#if - директива [C#]"
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# #if (Справочник по C#)
При обнаружении компилятором C\# директивы `#if`, за которой далее следует директива [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), компиляция кода между двумя директивами выполняется только в том случае, если определен указанный символ.  В отличие от C и C\+\+, символу нельзя присвоить числовое значение; оператор \#if языка C\# принадлежит типу Boolean, и он только проверяет, определен ли символ.  Например:  
  
```  
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 Операторы [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) \(равенство\), [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) \(неравенство\) можно использовать только для проверки возвращаемых ими значений [true](../../../csharp/language-reference/keywords/true.md) или [false](../../../csharp/language-reference/keywords/false.md).  Значение True означает, что символ определен.  Оператор `#if DEBUG` имеет то же значение, что и оператор `#if (DEBUG == true)`.  Можно использовать операторы &&\(и\) [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) \(или\) и [\!](../../../csharp/language-reference/operators/logical-negation-operator.md) \(not\) определить, были ли определены несколько символов.  Можно группировать символы и операторы при помощи скобок.  
  
## Заметки  
 Оператор `#if`, вместе с операторами [\#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) и [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), позволяет включать или исключать код на основе существования одного или нескольких символов.  Это особенно полезно при компиляции кода для построения отладки или при компиляции для определенной конфигурации.  
  
 Условная директива, начинающаяся с директивы `#if`, должна быть явным образом оканчиваться директивой `#endif`.  
  
 Директива `#define` позволяет определить символ, который, при его использовании в качестве выражения, переданного директиве `#if`, приведет к получению значения `true`.  
  
 Также можно определить символ с помощью параметра компилятора [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).  Для отмены определения символа служит директива [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Символ, определенный с помощью `/define` или `#define`, не конфликтует с одноименной переменной.  Имя переменной не должно передаваться директиве предварительной обработки, а символ может вычисляться только директивой предварительной обработки.  
  
 Область символа создается с помощью директивы `#define` в файле, в котором символ был определен.  
  
## Пример  
  
```  
// preprocessor_if.cs  
#define DEBUG #define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
  **DEBUG and MYTEST are defined**   
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)