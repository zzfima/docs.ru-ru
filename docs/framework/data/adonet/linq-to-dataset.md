---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 4995512336ee9eb6e33df011757ed533db57e76e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783784"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="67e91-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="67e91-102">LINQ to DataSet</span></span>
<span data-ttu-id="67e91-103">LINQ to DataSet упрощает и ускоряет выполнение запросов к данным, <xref:System.Data.DataSet> кэшированным в объекте.</span><span class="sxs-lookup"><span data-stu-id="67e91-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="67e91-104">В частности, LINQ to DataSet упрощает выполнение запросов, позволяя разработчикам писать запросы с самого языка программирования, а не с помощью отдельного языка запросов.</span><span class="sxs-lookup"><span data-stu-id="67e91-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="67e91-105">Это особенно удобно для разработчиков Visual Studio, которые теперь могут использовать преимущества проверки синтаксиса во время компиляции, статическую типизацию и поддержку IntelliSense, предоставляемую Visual Studio в своих запросах.</span><span class="sxs-lookup"><span data-stu-id="67e91-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="67e91-106">LINQ to DataSet также можно использовать для запроса данных, консолидированных из одного или нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="67e91-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="67e91-107">Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="67e91-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="67e91-108">В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="67e91-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="67e91-109">Функции LINQ to DataSet предоставляются главным образом через методы расширения в <xref:System.Data.DataRowExtensions> классах и. <xref:System.Data.DataTableExtensions></span><span class="sxs-lookup"><span data-stu-id="67e91-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="67e91-110">LINQ to DataSet строится на основе существующей архитектуры ADO.NET и не предназначена для замены ADO.NET в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="67e91-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="67e91-111">Существующий код ADO.NET будет продолжать работать в приложении LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="67e91-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="67e91-112">Отношение LINQ to DataSet к ADO.NET и хранилищу данных показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="67e91-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Схема, показывающая, что LINQ to DataSet основан на поставщике ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="67e91-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="67e91-114">In This Section</span></span>  
 [<span data-ttu-id="67e91-115">Начало работы</span><span class="sxs-lookup"><span data-stu-id="67e91-115">Getting Started</span></span>](getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="67e91-116">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="67e91-116">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="67e91-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="67e91-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="67e91-118">См. также</span><span class="sxs-lookup"><span data-stu-id="67e91-118">See also</span></span>

- [<span data-ttu-id="67e91-119">LINQ — C#</span><span class="sxs-lookup"><span data-stu-id="67e91-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="67e91-120">LINQ — Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67e91-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="67e91-121">LINQ и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="67e91-121">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="67e91-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="67e91-122">ADO.NET</span></span>](index.md)
