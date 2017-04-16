---
title: "Как отключить отложенную загрузку | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как отключить отложенную загрузку
Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`.  Для получения дополнительной информации см. [Сравнение отложенной и немедленной загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
> [!NOTE]
>  Отложенная загрузка отключается при отключении отслеживания объекта.  Для получения дополнительной информации см. [Как получать данные в режиме только для чтения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).  
  
## Пример  
 В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## См. также  
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [Выполнение запросов к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)