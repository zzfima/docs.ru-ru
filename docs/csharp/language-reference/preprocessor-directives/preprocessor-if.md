---
title: "#<a name=\"if-c-reference--microsoft-docs\"></a>If (Справочник по C#) | Документация Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#if'
dev_langs:
- CSharp
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: 4fc51446d297015d9e492703c9b1868c3b513c53
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="if-c-reference"></a>#if (Справочник по C#)
Когда компилятор C# встречает директиву `#if`, за которой следует директива [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), код между этими директивами он компилирует только в том случае, когда определен указанный символ.  В отличие от C и C++, здесь нельзя назначить символу числовое значение. Оператор #if языка C# является логическим и проверяет только одно условие — определен ли указанный символ. Например:  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 Операторы [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (равенство) и [! =](../../../csharp/language-reference/operators/not-equal-operator.md) (неравенство) вы можете использовать только для проверки значений [true](../../../csharp/language-reference/keywords/true.md) или [false](../../../csharp/language-reference/keywords/false.md). Значение true означает, что символ определен. Инструкция `#if DEBUG` имеет то же значение, что и `#if (DEBUG == true)`. Вы можете использовать операторы [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (логическое И), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (логическое ИЛИ) и [!](../../../csharp/language-reference/operators/logical-negation-operator.md) (логическое НЕ) для проверки нескольких символов. Можно также группировать символы и операторы при помощи скобок.  
  
## <a name="remarks"></a>Примечания  
 `#if`, как и директивы [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) и [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), позволяет включить или исключить код в зависимости от существования одного или нескольких символов. Это может быть полезно при компиляции кода для отладки или для определенной конфигурации.  
  
 Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.  
  
 `#define` позволяет определить символ, чтобы директива `#if`, которой передается этот символ, возвращала значение `true`.  
  
 Также символ можно определить с помощью параметра компилятора [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md). Для отмены определения символа служит директива [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Символ, определенный с помощью `/define` или `#define`, не конфликтует с одноименной переменной. Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.  
  
 Символ, создаваемый с помощью `#define`, будет определен в пределах того файл, в котором он определен.  
  
## <a name="example"></a>Пример  
  
```csharp
// preprocessor_if.cs  
#define DEBUG#define MYTEST  
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
  
 **Определение символов DEBUG и MYTEST**   
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)

