---
title: "Создание объекта DataReader"
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
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 05b3943613a6ab03e77dee7fb8262029618b5c7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-datareader"></a><span data-ttu-id="98587-102">Создание объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="98587-102">Creating a DataReader</span></span>
<span data-ttu-id="98587-103">Классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet> имеют метод <xref:System.Data.DataTable.CreateDataReader%2A>, возвращающий содержимое объекта <xref:System.Data.DataTable> или содержимое объекта <xref:System.Data.DataSet> коллекции <xref:System.Data.DataSet.Tables%2A> в виде одного или нескольких доступных для чтения результирующих наборов с последовательным доступом.</span><span class="sxs-lookup"><span data-stu-id="98587-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98587-104">Пример</span><span class="sxs-lookup"><span data-stu-id="98587-104">Example</span></span>  
 <span data-ttu-id="98587-105">Следующее приложение командной строки создает экземпляр <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="98587-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="98587-106">Затем в примере заполненный <xref:System.Data.DataTable> процедура, которая вызывает <xref:System.Data.DataTable.CreateDataReader%2A> метод, который выполняет проход по результатам, содержащихся в <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="98587-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="98587-107">В этом примере в окне консоли отображаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="98587-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="98587-108">См. также</span><span class="sxs-lookup"><span data-stu-id="98587-108">See Also</span></span>  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [<span data-ttu-id="98587-109">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="98587-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="98587-110">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98587-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
