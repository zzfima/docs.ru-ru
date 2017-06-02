---
title: "Получение одиночного значения из базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Получение одиночного значения из базы данных
Может возникнуть необходимость вернуть сведения из базы данных, которые представляют собой одиночное значение, а не форму таблицы или поток данных.  Допустим, может потребоваться вернуть результат агрегатной функции, например COUNT\(\*\), SUM\(Price\) или AVG\(Quantity\).  Объект **Command** предоставляет возможность возвращать одиночные значения при помощи метода **ExecuteScalar**.  Метод **ExecuteScalar** возвращает значение первого столбца первой строки результирующего набора в виде скалярного значения.  
  
 В следующем примере кода в базу данных при помощи <xref:System.Data.SqlClient.SqlCommand> вставляется новое значение.  Метод <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> используется, чтобы вернуть значение столбца идентификатора для вставленной записи.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## См. также  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Выполнение команды](../../../../docs/framework/data/adonet/executing-a-command.md)   
 [DbConnection, DbCommand и DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)