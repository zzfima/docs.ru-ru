---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 92be418e38039757437e6e673f39a7baef011528
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221786"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="21b86-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="21b86-102">LINQ to DataSet</span></span>
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="21b86-103">упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="21b86-103">makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="21b86-104">В частности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяя разработчикам писать запросы в языке программирования, а не используя отдельный язык запросов.</span><span class="sxs-lookup"><span data-stu-id="21b86-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="21b86-105">Это особенно полезно для разработчиков Visual Studio, которые теперь могут воспользоваться преимуществами проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые Visual Studio в своих запросах.</span><span class="sxs-lookup"><span data-stu-id="21b86-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="21b86-106">Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках.</span><span class="sxs-lookup"><span data-stu-id="21b86-106">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="21b86-107">Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="21b86-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="21b86-108">В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="21b86-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="21b86-109">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Предоставляется в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы.</span><span class="sxs-lookup"><span data-stu-id="21b86-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] <span data-ttu-id="21b86-110">основывается на и использует существующую [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] архитектуры и не предназначен для замены [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="21b86-110">builds on and uses the existing [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architecture, and is not meant to replace [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] in application code.</span></span> <span data-ttu-id="21b86-111">Существующий код ADO.NET 2.0 продолжит работать в приложении [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21b86-111">Existing ADO.NET 2.0 code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="21b86-112">Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] и хранилищем данных показана на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="21b86-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] and the data store is illustrated in the following diagram.</span></span>  
  
 ![Схема, показывающая, что LINQ to DataSet основана на поставщике ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="21b86-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="21b86-114">In This Section</span></span>  
 [<span data-ttu-id="21b86-115">Начало работы</span><span class="sxs-lookup"><span data-stu-id="21b86-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="21b86-116">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="21b86-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="21b86-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="21b86-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="21b86-118">См. также</span><span class="sxs-lookup"><span data-stu-id="21b86-118">See also</span></span>

- [<span data-ttu-id="21b86-119">LINQ — C#</span><span class="sxs-lookup"><span data-stu-id="21b86-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="21b86-120">LINQ — Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21b86-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="21b86-121">LINQ и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="21b86-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="21b86-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="21b86-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
