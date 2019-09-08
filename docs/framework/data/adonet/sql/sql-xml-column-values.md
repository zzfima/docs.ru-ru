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
# <a name="sql-xml-column-values"></a><span data-ttu-id="d7cba-102">Значения столбцов XML SQL</span><span class="sxs-lookup"><span data-stu-id="d7cba-102">SQL XML Column Values</span></span>
<span data-ttu-id="d7cba-103">SQL Server поддерживает `xml` тип данных, и разработчики могут извлекать результирующие наборы, включая этот тип, с помощью <xref:System.Data.SqlClient.SqlCommand> стандартного поведения класса.</span><span class="sxs-lookup"><span data-stu-id="d7cba-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="d7cba-104">Значения столбца `xml` извлекаются точно так же, как и значения любого столбца (например, в <xref:System.Data.SqlClient.SqlDataReader>), но если с содержимым этого столбца необходимо работать в формате XML, то следует использовать <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d7cba-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7cba-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d7cba-105">Example</span></span>  
 <span data-ttu-id="d7cba-106">Следующее консольное приложение выбирает две строки, каждая из которых `xml` содержит столбец, из таблицы **Sales. Store** в базе данных <xref:System.Data.SqlClient.SqlDataReader> AdventureWorks в экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d7cba-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="d7cba-107">Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> объекта <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="d7cba-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="d7cba-108">Это значение сохраняется в <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d7cba-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d7cba-109">Обратите внимание, что следует использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не метод <xref:System.Data.IDataRecord.GetValue%2A>, если необходимо присвоить содержимое переменной <xref:System.Data.SqlTypes.SqlXml>; метод <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в виде строки.</span><span class="sxs-lookup"><span data-stu-id="d7cba-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7cba-110">Образец базы данных **AdventureWorks** по умолчанию не устанавливается при установке SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7cba-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="d7cba-111">Чтобы установить его, запустите программу установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7cba-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d7cba-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d7cba-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="d7cba-113">Данные XML в SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7cba-113">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="d7cba-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7cba-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
