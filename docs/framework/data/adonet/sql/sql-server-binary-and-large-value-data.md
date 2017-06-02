---
title: "Двоичные данные и данные большого размера SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Двоичные данные и данные большого размера SQL Server
В SQL Server появился описатель `max`, расширяющий возможности хранения типов данных `varchar`, `nvarchar` и `varbinary`.  Типы данных `varchar(max)`, `nvarchar(max)` и `varbinary(max)` называются *типами данных большого размера*.  Типы данных большого размера можно использовать для хранения данных размером до 2^31\-1 байт.  
  
 В SQL Server 2008 появился атрибут FILESTREAM, который является не типом данных, а определяемым для столбца атрибутом, позволяющим хранить данные большого размера не в базе данных, а в файловой системе.  
  
## В этом подразделе  
 [Изменение данных большого размера \(max\) в ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Содержит описание работы с большими типами данных.  
  
 [Данные FILESTREAM](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Описывается работа с данными большого размера, хранящимися в SQL Server 2008 с указанием атрибута FILESTREAM.  
  
## См. также  
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Операции с данными SQL Server в ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)   
 [Получение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)