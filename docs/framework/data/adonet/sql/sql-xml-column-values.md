---
title: "Значения столбцов XML SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 087a0583c8655f28fcc308768bf75fcaa1d36ef9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="55b6d-102">Значения столбцов XML SQL</span><span class="sxs-lookup"><span data-stu-id="55b6d-102">SQL XML Column Values</span></span>
<span data-ttu-id="55b6d-103">В [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] поддерживается тип данных `xml`, поэтому разработчики могут получать результирующие наборы с данными этого типа с помощью стандартных средств класса <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="55b6d-103">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="55b6d-104">Значения столбца `xml` извлекаются точно так же, как и значения любого столбца (например, в <xref:System.Data.SqlClient.SqlDataReader>), но если с содержимым этого столбца необходимо работать в формате XML, то следует использовать <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="55b6d-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55b6d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="55b6d-105">Example</span></span>  
 <span data-ttu-id="55b6d-106">Следующее консольное приложение выбирает двух строк, каждая из которых содержит `xml` столбец, из **Sales.Store** в таблицу **AdventureWorks** базы данных для <xref:System.Data.SqlClient.SqlDataReader> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="55b6d-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="55b6d-107">Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> объекта <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="55b6d-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="55b6d-108">Это значение сохраняется в <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="55b6d-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="55b6d-109">Обратите внимание, что следует использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не метод <xref:System.Data.IDataRecord.GetValue%2A>, если необходимо присвоить содержимое переменной <xref:System.Data.SqlTypes.SqlXml>; метод <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в виде строки.</span><span class="sxs-lookup"><span data-stu-id="55b6d-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55b6d-110">**AdventureWorks** образца базы данных не устанавливается по умолчанию при установке [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55b6d-110">The **AdventureWorks** sample database is not installed by default when you install [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="55b6d-111">Чтобы установить его, запустите программу установки [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55b6d-111">You can install it by running [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="55b6d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="55b6d-112">See Also</span></span>  
 <xref:System.Data.SqlTypes.SqlXml>  
 [<span data-ttu-id="55b6d-113">Данные XML в SQL Server</span><span class="sxs-lookup"><span data-stu-id="55b6d-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [<span data-ttu-id="55b6d-114">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55b6d-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
