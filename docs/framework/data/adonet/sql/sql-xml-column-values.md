---
title: Значения столбцов XML SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 03b09d3a53c725bb0e84ba6b5d98944267bc564c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780802"
---
# <a name="sql-xml-column-values"></a>Значения столбцов XML SQL
SQL Server поддерживает `xml` тип данных, и разработчики могут извлекать результирующие наборы, включая этот тип, с помощью <xref:System.Data.SqlClient.SqlCommand> стандартного поведения класса. Значения столбца `xml` извлекаются точно так же, как и значения любого столбца (например, в <xref:System.Data.SqlClient.SqlDataReader>), но если с содержимым этого столбца необходимо работать в формате XML, то следует использовать <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Пример  
 Следующее консольное приложение выбирает две строки, каждая из которых `xml` содержит столбец, из таблицы **Sales. Store** в базе данных <xref:System.Data.SqlClient.SqlDataReader> AdventureWorks в экземпляр. Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> объекта <xref:System.Data.SqlClient.SqlDataReader>. Это значение сохраняется в <xref:System.Xml.XmlReader>. Обратите внимание, что следует использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не метод <xref:System.Data.IDataRecord.GetValue%2A>, если необходимо присвоить содержимое переменной <xref:System.Data.SqlTypes.SqlXml>; метод <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в виде строки.  
  
> [!NOTE]
> Образец базы данных **AdventureWorks** по умолчанию не устанавливается при установке SQL Server. Чтобы установить его, запустите программу установки SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.SqlTypes.SqlXml>
- [Данные XML в SQL Server](xml-data-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
