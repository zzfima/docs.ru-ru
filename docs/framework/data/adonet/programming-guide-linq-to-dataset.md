---
title: "Руководство по программированию (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 298ff0c6bfc5bc251483de8e90e3a394a2337369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="e2d5e-102">Руководство по программированию (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e2d5e-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="e2d5e-103">Этот раздел содержит основные сведения о программировании с помощью [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и примеры.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2d5e-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e2d5e-104">In This Section</span></span>  
 [<span data-ttu-id="e2d5e-105">Запросы в LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e2d5e-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-106">Содержит сведения о создании запросов [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2d5e-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="e2d5e-107">Запросы к DataSet</span><span class="sxs-lookup"><span data-stu-id="e2d5e-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-108">Содержит инструкции по созданию запросов к объектам <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="e2d5e-109">Сравнение объектов DataRow</span><span class="sxs-lookup"><span data-stu-id="e2d5e-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-110">Объясняет, как использовать объект <xref:System.Data.DataRowComparer> для сравнения строк данных.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="e2d5e-111">Создание DataTable из запроса</span><span class="sxs-lookup"><span data-stu-id="e2d5e-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-112">Содержит сведения о создании <xref:System.Data.DataTable> из [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запроса с помощью <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="e2d5e-113">Как: реализовать метод CopyToDataTable\<T > где универсальный тип T не является DataRow</span><span class="sxs-lookup"><span data-stu-id="e2d5e-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="e2d5e-114">Описывает процедуру применения пользовательского метода `CopyToDataTable<T>`, где общий параметр T не принадлежит к типу <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="e2d5e-115">Универсальные методы Field и SetField</span><span class="sxs-lookup"><span data-stu-id="e2d5e-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-116">Предоставляет сведения об универсальных методах <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="e2d5e-117">Привязка данных и LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e2d5e-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-118">Описывает связывание данных с помощью объекта <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="e2d5e-119">Отладка запросов в LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e2d5e-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="e2d5e-120">Предоставляет сведения об отладке и устранении неполадок [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запросов.</span><span class="sxs-lookup"><span data-stu-id="e2d5e-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="e2d5e-121">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e2d5e-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="e2d5e-122">Описывает проблемы безопасности в запросах [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2d5e-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="e2d5e-123">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e2d5e-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="e2d5e-124">Содержит примеры запросов, использующих операторы [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2d5e-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e2d5e-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="e2d5e-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="e2d5e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e2d5e-126">See Also</span></span>  
 [<span data-ttu-id="e2d5e-127">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e2d5e-127">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [<span data-ttu-id="e2d5e-128">НЕ в СБОРКЕ: Общее руководство программирования на LINQ</span><span class="sxs-lookup"><span data-stu-id="e2d5e-128">NOT IN BUILD: LINQ General Programming Guide</span></span>](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049)  
 [<span data-ttu-id="e2d5e-129">LINQ Framework</span><span class="sxs-lookup"><span data-stu-id="e2d5e-129">LINQ Framework</span></span>](http://msdn.microsoft.com/en-us/897ea0fc-40db-4694-bbe5-7dd339d5bf94)
