---
title: "Как напрямую выполнять команды SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как напрямую выполнять команды SQL
Если предположить наличие подключения <xref:System.Data.Linq.DataContext>, для выполнения команд, которые не возвращают объекты, можно воспользоваться методом <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.  
  
## Пример  
 В следующем примере SQL Server увеличивает цену за единицу на 1.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## См. также  
 [Как напрямую выполнять SQL\-запросы](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)   
 [Взаимодействие с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)