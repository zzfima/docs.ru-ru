---
title: "Как объединить в пакеты отправку данных с помощью транзакций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как объединить в пакеты отправку данных с помощью транзакций
Для объединения запросов к базе данных в брекеты можно использовать класс <xref:System.Transactions.TransactionScope>.  Для получения дополнительной информации см. [Поддержка транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## Пример  
 В следующем коде отправка данных помещается в класс <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## См. также  
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Поддержка транзакций](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)