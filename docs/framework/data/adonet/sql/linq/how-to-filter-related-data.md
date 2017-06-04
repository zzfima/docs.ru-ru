---
title: "Как отфильтровать взаимосвязанные данные | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как отфильтровать взаимосвязанные данные
Чтобы указать вложенные запросы для ограничения объема извлекаемых данных, используется метод <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A>.  
  
## Пример  
 В следующем примере метод <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> ограничивает количество извлеченных заказов \(`Orders`\) заказами, которые сегодня не были доставлены.  Если не использовать этот подход, будут извлечены все заказы \(`Orders`\) даже в том случае, когда необходим только вложенный набор.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## См. также  
 [Выполнение запросов к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)