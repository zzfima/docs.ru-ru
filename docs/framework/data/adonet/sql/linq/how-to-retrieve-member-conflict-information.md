---
title: "Как получить сведения о конфликтах элементов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как получить сведения о конфликтах элементов
Класс <xref:System.Data.Linq.MemberChangeConflict> можно использовать для получения сведений об отдельных членах конфликта.  В этом же контексте можно предусмотреть пользовательскую обработку конфликта для любого члена.  Для получения дополнительной информации см. [Оптимистичный параллелизм. Общие сведения](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## Пример  
 Следующий код выполняет итерацию объектов <xref:System.Data.Linq.ObjectChangeConflict>.  Итерация выполняется для каждого объекта <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
>  Для предоставления сведений <xref:System.Data.Linq.MemberChangeConflict.Member%2A> добавьте пространство имен <xref:System.Reflection>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## См. также  
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)