---
title: Значения столбцов XML SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: b46c763e7cddfc7617c9a6a23428f83a54955ba0
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838907"
---
# <a name="sql-xml-column-values"></a>Значения столбцов XML SQL
SQL Server поддерживает `xml` тип данных, поэтому разработчики могут получать результирующие наборы с данными этого типа, с помощью стандартных средств <xref:System.Data.SqlClient.SqlCommand> класса. Значения столбца `xml` извлекаются точно так же, как и значения любого столбца (например, в <xref:System.Data.SqlClient.SqlDataReader>), но если с содержимым этого столбца необходимо работать в формате XML, то следует использовать <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Пример  
 Следующее консольное приложение выбираются две строки, каждая из которых содержит `xml` столбца, из **Sales.Store** в таблицу **AdventureWorks** базы данных для <xref:System.Data.SqlClient.SqlDataReader> экземпляра. Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> объекта <xref:System.Data.SqlClient.SqlDataReader>. Это значение сохраняется в <xref:System.Xml.XmlReader>. Обратите внимание, что следует использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не метод <xref:System.Data.IDataRecord.GetValue%2A>, если необходимо присвоить содержимое переменной <xref:System.Data.SqlTypes.SqlXml>; метод <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в виде строки.  
  
> [!NOTE]
>  **AdventureWorks** образца базы данных не устанавливается по умолчанию при установке SQL Server. Чтобы установить его, запустите программу установки SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.SqlTypes.SqlXml>  
 [Данные XML в SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
