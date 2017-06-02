---
title: "Значения столбца SQL XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Значения столбца SQL XML
В [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] поддерживается тип данных `xml`, поэтому разработчики могут получать результирующие наборы с данными этого типа с помощью стандартных средств класса <xref:System.Data.SqlClient.SqlCommand>.  Значения столбца `xml` извлекаются точно так же, как и значения любого столбца \(например, в <xref:System.Data.SqlClient.SqlDataReader>\), но если с содержимым этого столбца необходимо работать в формате XML, то следует использовать <xref:System.Xml.XmlReader>.  
  
## Пример  
 В следующем приложении командной строки в экземпляр <xref:System.Data.SqlClient.SqlDataReader> выбираются две строки, каждая из которых содержит значение столбца `xml` из таблицы **Sales.Store** базы данных **AdventureWorks**.  Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> объекта <xref:System.Data.SqlClient.SqlDataReader>.  Это значение сохраняется в <xref:System.Xml.XmlReader>.  Обратите внимание, что следует использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не метод <xref:System.Data.IDataRecord.GetValue%2A>, если необходимо присвоить содержимое переменной <xref:System.Data.SqlTypes.SqlXml>; метод <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в виде строки.  
  
> [!NOTE]
>  Образец базы данных **AdventureWorks** не устанавливается по умолчанию при установке [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Чтобы установить его, запустите программу установки [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## См. также  
 <xref:System.Data.SqlTypes.SqlXml>   
 [XML\-данные в SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)