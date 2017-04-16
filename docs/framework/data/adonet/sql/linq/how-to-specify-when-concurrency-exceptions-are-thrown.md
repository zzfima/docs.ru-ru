---
title: "Как указать, когда возникают исключения параллелизма | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как указать, когда возникают исключения параллелизма
Если в связи с конфликтами оптимистической блокировки обновление объектов не выполняется, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывается исключение <xref:System.Data.Linq.ChangeConflictException>.  Для получения дополнительной информации см. [Оптимистичный параллелизм. Общие сведения](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Перед отправкой изменений в базу данных можно указать момент возникновения исключений блокировки.  
  
-   Создавать исключение при первом сбое \(<xref:System.Data.Linq.ConflictMode>\).  
  
-   Завершить все попытки обновления, собрать все ошибки и сообщить о них в исключении \(<xref:System.Data.Linq.ConflictMode>\).  
  
 Созданное исключение <xref:System.Data.Linq.ChangeConflictException> предоставляет доступ к коллекции <xref:System.Data.Linq.ChangeConflictCollection>.  Данная коллекция содержит сведения о каждом конфликте \(сопоставленном с одной неудачной попыткой обновления\), включая доступ к коллекции <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>.  Каждый конфликт члена сопоставляется с одним членом в обновлении, которое привело к сбою проверки блокировки.  
  
## Пример  
 В следующем коде приведены примеры обоих значений.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## См. также  
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)