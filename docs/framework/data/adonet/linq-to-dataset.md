---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 36335f90c7850fa00a15e7112b7473637250c656
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306234"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="6a38a-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="6a38a-102">LINQ to DataSet</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="6a38a-103">упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6a38a-103">makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="6a38a-104">В частности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяя разработчикам писать запросы в языке программирования, а не используя отдельный язык запросов.</span><span class="sxs-lookup"><span data-stu-id="6a38a-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="6a38a-105">Это особенно полезно для разработчиков Visual Studio, которые теперь могут воспользоваться преимуществами проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые Visual Studio в своих запросах.</span><span class="sxs-lookup"><span data-stu-id="6a38a-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="6a38a-106">Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках.</span><span class="sxs-lookup"><span data-stu-id="6a38a-106">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="6a38a-107">Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="6a38a-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="6a38a-108">В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="6a38a-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="6a38a-109">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Предоставляется в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы.</span><span class="sxs-lookup"><span data-stu-id="6a38a-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="6a38a-110">основан на использует существующую архитектуру ADO.NET и не предназначен для замены ADO.NET в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="6a38a-110">builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="6a38a-111">Существующий код ADO.NET продолжит работать в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="6a38a-111">Existing ADO.NET code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="6a38a-112">Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] хранилищем для ADO.NET, а также данных показана на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="6a38a-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Схема, показывающая, что LINQ to DataSet основана на поставщике ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="6a38a-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6a38a-114">In This Section</span></span>  
 [<span data-ttu-id="6a38a-115">Начало работы</span><span class="sxs-lookup"><span data-stu-id="6a38a-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="6a38a-116">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="6a38a-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="6a38a-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6a38a-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="6a38a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6a38a-118">See also</span></span>

- [<span data-ttu-id="6a38a-119">LINQ — C#</span><span class="sxs-lookup"><span data-stu-id="6a38a-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6a38a-120">LINQ — Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a38a-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6a38a-121">LINQ и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6a38a-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="6a38a-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6a38a-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
