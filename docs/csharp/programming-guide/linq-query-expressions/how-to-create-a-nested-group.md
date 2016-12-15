---
title: "Практическое руководство. Создание вложенной группы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "группировка групп в запросах LINQ"
  - "группировка запросов LINQ"
  - "группы [LINQ в C#], вложенные"
  - "вложенные запросы [C#]"
  - "запросы [LINQ в C#], вложенные группы"
  - "выражения запросов [LINQ в C#], вложенные группы"
ms.assetid: f48c64af-6d4e-473c-ab27-02f78b5ec2b9
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Создание вложенной группы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующем примере показано, как создавать вложенные группы в выражении запроса [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].  Каждая группа, созданная в соответствии с годом или уровнем обучения, затем подразделяется на группы на основе имен учащихся.  
  
## Пример  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-create-a-nested-group_1.cs)]  
  
 Обратите внимание на то, что для выполнения итерации по внутренним элементам вложенной группы необходимы три вложенных цикла `foreach`.  
  
## Компиляция кода  
 В этом примере содержатся ссылки на объекты, определенные в примере приложения в разделе [Практическое руководство. Запрос коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md).  Чтобы скомпилировать и запустить этот метод, вставьте его в класс `StudentClass` в этом приложении и добавьте его вызов из метода `Main`.  
  
 Настраивая данный метод для своего приложения, помните, что для LINQ требуется [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] версии 3.5, и проект должен содержать ссылку на библиотеку System.Core.dll и директиву Using для библиотеки System.Linq.  Типы LINQ to SQL, LINQ to XML и LINQ to DataSet требуют дополнительных директив Using и ссылок.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)