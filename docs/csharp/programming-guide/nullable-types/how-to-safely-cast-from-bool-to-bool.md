---
title: "Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "приведение [C#], типы, допускающие значения NULL"
  - "типы, допускающие значения NULL [C#], приведение bool? к bool"
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Практическое руководство. Безопасное приведение bool? к bool (Руководство по программированию на C#)
Допускающий значение NULL тип `bool?` может содержать три различных значения: `true`, `false` и `null`.  Поэтому тип `bool?` нельзя использовать в условных выражениях, например, с операторами `if`, `for` или `while`.  Например, следующий код вызовет ошибку компиляции.  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Это запрещено, поскольку неизвестно, что обозначает `null` в контексте условного выражения.  Чтобы использовать `bool?` в условном операторе, сначала проверьте его свойство <xref:System.Nullable%601.HasValue%2A>, чтобы убедиться, что его значение отлично от `null`, а затем приведите его к `bool`.  Дополнительные сведения см. в описании [bool](../../../csharp/language-reference/keywords/bool.md).  Если выполняется приведение `bool?` со значением `null`, при проверке условия вызывается исключение <xref:System.InvalidOperationException>.  В следующем примере показан способ безопасного приведения от `bool?` к `bool`:  
  
## Пример  
  
```c#  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Буквенные ключевые слова](../../../csharp/language-reference/keywords/literal-keywords.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Оператор ??](../../../csharp/language-reference/operators/null-conditional-operator.md)