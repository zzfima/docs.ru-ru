---
title: "SKIP (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# SKIP (Entity SQL)
Вложенное предложение SKIP в предложении ORDER BY позволяет проводить физическое разбиение на страницы. Ключевое слово SKIP не может использоваться отдельно от предложения ORDER BY.  
  
## Синтаксис  
  
```  
  
[ SKIP n ]  
```  
  
## Аргументы  
 `n`  
 Число элементов, которые нужно пропустить.  
  
## Заметки  
 Если в предложении ORDER BY есть вложенное предложение SKIP, то результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP. Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.  
  
> [!NOTE]
>  Если в одном предложении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является недопустимым. Его следует переписать, заменив выражение TOP выражением LIMIT.  
  
> [!NOTE]
>  В [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)] использование предложения SKIP вместе с ORDER BY для неключевых столбцов может привести к возврату неверных результатов. Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк. Причина этого заключается в способе преобразования предложения SKIP для выполнения в [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]. Например, в следующем коде может быть пропущено более пяти строк, если столбец `E.NonKeyColumn` содержит повторяющиеся значения:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 Запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в [этом](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) примере использует для задания порядка сортировки объектов, возвращаемых инструкцией SELECT, оператор ORDER BY с предложением SKIP.  
  
## См. также  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)   
 [Практическое руководство. Разбивка на страницы результатов запроса](http://msdn.microsoft.com/ru-ru/ffc0f920-e7de-42e0-9b12-ef356421d030)   
 [Разбивка на страницы](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)   
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)