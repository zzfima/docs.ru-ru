---
title: "Как отобразить набор изменений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как отобразить набор изменений
Для просмотра изменений, отслеживаемых <xref:System.Data.Linq.DataContext>, можно воспользоваться методом <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.  
  
## Пример  
 В следующем примере извлекаются клиенты, находящиеся в Лондоне, город меняется на Париж, а изменения передаются назад в базу данных.  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 Этот код выводит следующий результат.  Обратите внимание, что в итоговой строке в конце указывается число внесенных изменений: 8.  
  
 `CustomerID: AROUT`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: BSBEV`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: CONSH`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: EASTC`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: NORTS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: PARIS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SEVES`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SPECD`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 ``  
  
 `Total changes: {Added: 0, Removed: 0, Modified: 8}`  
  
## См. также  
 [Поддержка отладки](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)