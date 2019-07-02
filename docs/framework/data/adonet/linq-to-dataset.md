---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: c4069ef760877935c4ce194144d131d0dc58b4d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504363"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="305ab-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="305ab-102">LINQ to DataSet</span></span>
<span data-ttu-id="305ab-103">LINQ to DataSet позволяет проще и быстрее для запросов к данным кэшируются в <xref:System.Data.DataSet> объекта.</span><span class="sxs-lookup"><span data-stu-id="305ab-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="305ab-104">В частности LINQ to DataSet упрощает создание запросов, позволяя разработчикам писать запросы в языке программирования, а не используя отдельный язык запросов.</span><span class="sxs-lookup"><span data-stu-id="305ab-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="305ab-105">Это особенно полезно для разработчиков Visual Studio, которые теперь могут воспользоваться преимуществами проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые Visual Studio в своих запросах.</span><span class="sxs-lookup"><span data-stu-id="305ab-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="305ab-106">Также можно использовать LINQ to DataSet для запросов к данным, находящимся в одной или нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="305ab-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="305ab-107">Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="305ab-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="305ab-108">В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="305ab-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="305ab-109">LINQ to DataSet функциональность предоставляется в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы.</span><span class="sxs-lookup"><span data-stu-id="305ab-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="305ab-110">LINQ to DataSet основана на и использует существующую архитектуру ADO.NET и не предназначен для замены ADO.NET в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="305ab-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="305ab-111">Существующий код ADO.NET будет продолжать работать в LINQ to DataSet приложения.</span><span class="sxs-lookup"><span data-stu-id="305ab-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="305ab-112">На следующей схеме показана связь между LINQ to DataSet ADO.NET и хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="305ab-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Схема, показывающая, что LINQ to DataSet основана на поставщике ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="305ab-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="305ab-114">In This Section</span></span>  
 [<span data-ttu-id="305ab-115">Начало работы</span><span class="sxs-lookup"><span data-stu-id="305ab-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="305ab-116">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="305ab-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="305ab-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="305ab-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="305ab-118">См. также</span><span class="sxs-lookup"><span data-stu-id="305ab-118">See also</span></span>

- [<span data-ttu-id="305ab-119">LINQ — C#</span><span class="sxs-lookup"><span data-stu-id="305ab-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="305ab-120">LINQ — Visual Basic</span><span class="sxs-lookup"><span data-stu-id="305ab-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="305ab-121">LINQ и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="305ab-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="305ab-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="305ab-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
