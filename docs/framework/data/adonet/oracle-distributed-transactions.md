---
title: "Распределенные транзакции Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Распределенные транзакции Oracle
Объект <xref:System.Data.OracleClient.OracleConnection> автоматически прикрепляется к существующей распределенной транзакции, если он определяет, что транзакция активна.  Автоматическое прикрепление к транзакции происходит при открытии соединения или его получении из пула соединений.  Автоматическое прикрепление к существующим транзакциям можно отменить, задав  
  
```  
Enlist=false  
```  
  
 в качестве параметра строки соединения для <xref:System.Data.OracleClient.OracleConnection>.  
  
## См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)