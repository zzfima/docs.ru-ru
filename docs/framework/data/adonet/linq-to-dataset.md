---
title: LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de0f11149c2ec587372b9e25f39f35f8552503c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-dataset"></a><span data-ttu-id="36ed4-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="36ed4-102">LINQ to DataSet</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="36ed4-103"> упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="36ed4-103"> makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="36ed4-104">В частности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяет разработчикам писать запросы на языке программирования, а не с помощью отдельный язык запросов.</span><span class="sxs-lookup"><span data-stu-id="36ed4-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="36ed4-105">Это особенно полезно для [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] разработчиков, которые теперь могут воспользоваться преимуществами проверки синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] в запросах.</span><span class="sxs-lookup"><span data-stu-id="36ed4-105">This is especially useful for [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] in their queries.</span></span>  
  
 <span data-ttu-id="36ed4-106">Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках.</span><span class="sxs-lookup"><span data-stu-id="36ed4-106">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="36ed4-107">Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="36ed4-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="36ed4-108">В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="36ed4-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="36ed4-109">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Функциональные возможности представлены в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы.</span><span class="sxs-lookup"><span data-stu-id="36ed4-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="36ed4-110">выполняет построение на и использует ее [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] архитектуры и не предназначен для замены [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="36ed4-110"> builds on and uses the existing [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architecture, and is not meant to replace [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] in application code.</span></span> <span data-ttu-id="36ed4-111">Существующий код ADO.NET 2.0 продолжит работать в приложении [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36ed4-111">Existing ADO.NET 2.0 code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="36ed4-112">Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] и хранилищем данных показана на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="36ed4-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] and the data store is illustrated in the following diagram.</span></span>  
  
 <span data-ttu-id="36ed4-113">![Технология LINQ to DataSet основан на поставщике ADO.NET](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span><span class="sxs-lookup"><span data-stu-id="36ed4-113">![LINQ to DataSet is based on the ADO.NET Provider](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36ed4-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="36ed4-114">In This Section</span></span>  
 [<span data-ttu-id="36ed4-115">Начало работы</span><span class="sxs-lookup"><span data-stu-id="36ed4-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="36ed4-116">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="36ed4-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="36ed4-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="36ed4-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="36ed4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="36ed4-118">See Also</span></span>  
 [<span data-ttu-id="36ed4-119">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="36ed4-119">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="36ed4-120">LINQ и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="36ed4-120">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [<span data-ttu-id="36ed4-121">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="36ed4-121">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
