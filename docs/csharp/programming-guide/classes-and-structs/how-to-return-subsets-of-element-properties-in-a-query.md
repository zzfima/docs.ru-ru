---
title: "Практическое руководство. Возвращение поднаборов свойств элементов в запросе (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "анонимные типы [C#], для подмножеств свойств элементов"
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# Практическое руководство. Возвращение поднаборов свойств элементов в запросе (Руководство по программированию в C#)
Используйте анонимный тип в выражении запроса, если выполняются оба этих условия:  
  
-   Требуется возвратить только некоторые свойства каждого из исходных элементов.  
  
-   Не требуется сохранять результаты запроса за пределами области действия метода, в котором был выполнен запрос.  
  
 Если требуется возвратить одно свойство или поле из каждого исходного элемента, можно просто воспользоваться оператором "точка" в предложении `select`.  Например, чтобы возвратить только `ID` для каждого `student`, создайте следующее предложение `select`:  
  
```  
select student.ID;  
```  
  
## Пример  
 В следующем примере показывается, как использовать анонимный тип для возврата только поднабора свойств каждого из исходных элементов, соответствующих указанному условию.  
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#31)]  
  
 Обратите внимание, что анонимный тип использует имена исходного элемента для его свойств, если имена не заданы.  Чтобы назначить свойствам в анонимном типе новые имена, укажите следующий оператор `select`:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Если попытаться вставить его в предыдущий пример, то потребуется изменить и оператор `Console.WriteLine`:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## Компиляция кода  
  
-   Для выполнения этого кода скопируйте класс в проект консольного приложения на языке Visual C\#, которое было создано в среде разработки [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  По умолчанию этот проект предназначен для версии 3.5 платформы [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] и имеет ссылку на библиотеку System.Core.dll и директиву `using` для System.Linq.  Если одно или более требований в проекте отсутствуют, их можно добавить вручную.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)