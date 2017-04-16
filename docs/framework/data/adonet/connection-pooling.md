---
title: "Организация пулов соединений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Организация пулов соединений
На соединение с источником данных может требоваться значительное время.  Чтобы свести к минимуму затраты на открытие соединения, в ADO.NET используется техника *пулов соединений*, которая позволяет минимизировать затраты на часто открываемые и закрываемые соединения.  Пулы соединений обрабатываются для поставщиков данных .NET Framework по\-разному.  
  
## В этом подразделе  
 [Организация пулов соединений SQL Server \(ADO.NET\)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 Общие сведения о пулах соединений и описание принципов работы пулов соединений в [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  
  
 [Организация пулов соединений OLE DB, ODBC, and Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.  
  
## См. также  
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)