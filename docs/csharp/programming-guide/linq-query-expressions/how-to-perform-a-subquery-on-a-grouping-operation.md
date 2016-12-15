---
title: "Практическое руководство. Вложенный запрос в операции группирования (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "группировка запросов LINQ [C#]"
  - "группы [C#], выражения запросов LINQ"
  - "группы [LINQ в C#], подзапросы"
  - "запросы [LINQ в C#], группирование"
  - "запросы [LINQ в C#], подзапросы"
  - "выражения запросов [LINQ в C#], группирование"
  - "выражения запросов [LINQ в C#], подзапросы"
  - "подзапросы [C#]"
ms.assetid: 7b0805cd-53b4-429d-86b6-d37fb08f2c95
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Вложенный запрос в операции группирования (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом разделе показано два разных способа создания запроса, упорядочивающего исходные данные в группы, и затем выполняющего вложенный запрос с каждой группой в отдельности.  Основной способ в каждом примере заключается в группировании исходных элементов при помощи *продолжения* с именем `newGroup` с последующим создание нового вложенного запроса по `newGroup`.  Это вложенный запрос выполняется для каждой новой группы, создаваемой внешним запросов.  В этом конкретном примере следует обратить внимание на то, что в конечном итоге получается не группа, а простая последовательность анонимных типов.  
  
 Дополнительные сведения о способах группирования см. в разделе [Предложение group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Дополнительные сведения о продолжениях см. в разделе [into](../../../csharp/language-reference/keywords/into.md).  В следующем примере в качестве источника данных используется структура данных в памяти, но те же принципы действуют для любого типа источника данных [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].  
  
## Пример  
 [!code-cs[csProgGuideLINQ#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
  
## Компиляция кода  
 В этом примере содержатся ссылки на объекты, определенные в примере приложения в разделе [Практическое руководство. Запрос коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md).  Чтобы скомпилировать и запустить этот метод, вставьте его в класс `StudentClass` в этом приложении и добавьте его вызов из метода `Main`.  
  
 Настраивая данный метод для своего приложения, помните, что для LINQ требуется [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] версии 3.5, и проект должен содержать ссылку на библиотеку System.Core.dll и директиву Using для библиотеки System.Linq.  Типы LINQ to SQL, LINQ to XML и LINQ to DataSet требуют дополнительных директив Using и ссылок.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)