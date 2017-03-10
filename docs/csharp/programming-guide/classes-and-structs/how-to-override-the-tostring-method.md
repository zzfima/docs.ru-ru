---
title: "Практическое руководство. Переопределение метода ToString (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "наследование [C#], переопределение методов OnPaint и ToString"
  - "ToString - метод, переопределение в C#"
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Переопределение метода ToString (Руководство по программированию на C#)
Каждый класс или структура в C\# неявно наследует классу <xref:System.Object>.  Поэтому каждый объект в языке C\# получает метод <xref:System.Object.ToString%2A>, который возвращает строковое представление данного объекта.  Например, все переменные типа `int` имеют метод `ToString`, который позволяет им возвращать содержимое этой переменной в виде строки:  
  
 [!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-override-the-tost_1.cs)]  
  
 При создании пользовательского класса или структуры необходимо переопределить метод <xref:System.Object.ToString%2A>, чтобы передать информацию о типе клиентскому коду.  
  
 Дополнительные сведения об использовании строк форматирования и другие типы пользовательского форматирования с методом `ToString` см. в разделе [Типы форматирования](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  
  
> [!IMPORTANT]
>  При принятии решения относительно того, какая информация должна будет предоставляться посредством этого метода, подумайте, будет ли создаваемый класс или структура когда\-либо использоваться ненадежным кодом.  Постарайтесь не предоставлять информацию, которая может быть использована вредоносным кодом.  
  
### Переопределение метода ToString в классе или структуре  
  
1.  Объявите метод `ToString` со следующими модификаторами и типом возвращаемого значения:  
  
    ```c#  
    public override string ToString(){}  
    ```  
  
2.  Реализуйте этот метод таким образом, чтобы он возвращал строку.  
  
     В приведенном ниже примере возвращается не только имя класса, но и специфические данные для конкретного экземпляра класса.  
  
     [!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-override-the-tost_2.cs)]  
  
     Метод `ToString` можно проверить с помощью показанного ниже кода.  
  
     [!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-override-the-tost_3.cs)]  
  
## См. также  
 <xref:System.IFormattable>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [string](../../../csharp/language-reference/keywords/string.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [виртуальные](../../../csharp/language-reference/keywords/virtual.md)   
 [Типы форматирования](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)