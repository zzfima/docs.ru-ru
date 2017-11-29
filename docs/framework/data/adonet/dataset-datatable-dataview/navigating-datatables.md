---
title: "Навигация по таблицам данных"
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
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cecceb94caf4d1c0a9a05c48485f7e79a70bfce6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="navigating-datatables"></a><span data-ttu-id="2bbd5-102">Навигация по таблицам данных</span><span class="sxs-lookup"><span data-stu-id="2bbd5-102">Navigating DataTables</span></span>
<span data-ttu-id="2bbd5-103">Объект <xref:System.Data.DataTableReader> получает содержимое одного или нескольких объектов <xref:System.Data.DataTable> в виде одного или нескольких однопроходных результирующих наборов, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="2bbd5-104">Объект <xref:System.Data.DataTableReader> может содержать несколько результирующих наборов, если он создан методом <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="2bbd5-105">Если имеется несколько результирующих наборов, метод <xref:System.Data.DataTableReader.NextResult%2A> продвигает курсор к следующему результирующему набору.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="2bbd5-106">Это однопроходной процесс.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-106">This is a forward-only process.</span></span> <span data-ttu-id="2bbd5-107">Вернуться к предыдущему результирующему набору невозможно.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bbd5-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2bbd5-108">Example</span></span>  
 <span data-ttu-id="2bbd5-109">В следующем примере `TestConstructor` метод создает два <xref:System.Data.DataTable> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="2bbd5-110">Чтобы продемонстрировать работу конструктора для <xref:System.Data.DataTableReader> класса, в примере создается новый **DataTableReader** на основе массива, содержащего две **DataTables**и выполняет простую операцию выводя содержимое первых столбцов в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="2bbd5-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2bbd5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2bbd5-111">See Also</span></span>  
 [<span data-ttu-id="2bbd5-112">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="2bbd5-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="2bbd5-113">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2bbd5-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
