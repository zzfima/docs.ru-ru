---
title: Наборы данных, таблицы данных и объекты DataView
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 9c57f75dd94f3fbda74c13a5d5773825051fe416
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105733"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="39640-102">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="39640-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="39640-103">ADO.NET <xref:System.Data.DataSet> - расположенное в оперативной памяти представление данных, обеспечивающее согласованную реляционную программную модель независимо от источника данных.</span><span class="sxs-lookup"><span data-stu-id="39640-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="39640-104"><xref:System.Data.DataSet> представляет полный набор данных, включая таблицы, содержащие, упорядочивающие и ограничивающие данные, а также связи между таблицами.</span><span class="sxs-lookup"><span data-stu-id="39640-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="39640-105">Существует несколько способов работы с <xref:System.Data.DataSet>, которые могут применяться отдельно или в сочетании.</span><span class="sxs-lookup"><span data-stu-id="39640-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="39640-106">Можно выполнить следующие действия: </span><span class="sxs-lookup"><span data-stu-id="39640-106">You can:</span></span>  
  
-   <span data-ttu-id="39640-107">Программно создать <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> и <xref:System.Data.Constraint> внутри <xref:System.Data.DataSet> и заполнить таблицы данными.</span><span class="sxs-lookup"><span data-stu-id="39640-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
-   <span data-ttu-id="39640-108">Заполнить <xref:System.Data.DataSet> таблицами данных из существующего реляционного источника данных с помощью `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="39640-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
-   <span data-ttu-id="39640-109">Загрузить и сохранить содержимое <xref:System.Data.DataSet> с помощью XML-кода.</span><span class="sxs-lookup"><span data-stu-id="39640-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="39640-110">Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="39640-110">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="39640-111">Строго типизированный <xref:System.Data.DataSet> также можно передавать с помощью веб-службы с поддержкой XML-кода.</span><span class="sxs-lookup"><span data-stu-id="39640-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="39640-112">Конструкция <xref:System.Data.DataSet> делает его идеальным для передачи данных с помощью веб-служб с поддержкой XML-кода.</span><span class="sxs-lookup"><span data-stu-id="39640-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="39640-113">Общие сведения об XML-веб-службах см. в разделе [Общие сведения об XML-веб-службах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="39640-113">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="39640-114">Пример использования <xref:System.Data.DataSet> из XML-веб-службы см. в разделе [Потребление набора данных из веб-службы XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="39640-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39640-115">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="39640-115">In This Section</span></span>  
 [<span data-ttu-id="39640-116">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="39640-116">Creating a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 <span data-ttu-id="39640-117">Описывает синтаксис, необходимый для создания экземпляра <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="39640-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="39640-118">Добавление новой таблицы данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="39640-118">Adding a DataTable to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="39640-119">Описывает создание и добавление таблиц и столбцов в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="39640-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="39640-120">Добавление отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="39640-120">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 <span data-ttu-id="39640-121">Описывает создание связей между таблицами <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="39640-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="39640-122">Навигация по отношениям DataRelation</span><span class="sxs-lookup"><span data-stu-id="39640-122">Navigating DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 <span data-ttu-id="39640-123">Описывает использование связей между таблицами <xref:System.Data.DataSet> для возвращения дочерних или родительских строк связи типа «родитель-потомок».</span><span class="sxs-lookup"><span data-stu-id="39640-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="39640-124">Слияние содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="39640-124">Merging DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 <span data-ttu-id="39640-125">Описывает процесс слияния содержимого одного <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или массива <xref:System.Data.DataRow> с <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="39640-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="39640-126">Копирование содержимого набора данных</span><span class="sxs-lookup"><span data-stu-id="39640-126">Copying DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 <span data-ttu-id="39640-127">Описывает создание копии <xref:System.Data.DataSet>, которая может содержать схему, а также указанные данные.</span><span class="sxs-lookup"><span data-stu-id="39640-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="39640-128">Обработка событий наборов данных</span><span class="sxs-lookup"><span data-stu-id="39640-128">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 <span data-ttu-id="39640-129">Описывает события <xref:System.Data.DataSet> и их использование.</span><span class="sxs-lookup"><span data-stu-id="39640-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="39640-130">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="39640-130">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 <span data-ttu-id="39640-131">Обсуждается, что такое типизированный <xref:System.Data.DataSet> и как его создавать и использовать.</span><span class="sxs-lookup"><span data-stu-id="39640-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="39640-132">DataTables</span><span class="sxs-lookup"><span data-stu-id="39640-132">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="39640-133">Описывает создание <xref:System.Data.DataTable>, определение схемы и управление данными.</span><span class="sxs-lookup"><span data-stu-id="39640-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="39640-134">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="39640-134">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 <span data-ttu-id="39640-135">Описывает создание и использование <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="39640-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="39640-136">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="39640-136">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 <span data-ttu-id="39640-137">Описывает создание `DataViews` и работу с ними, а также работу с событиями <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="39640-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="39640-138">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="39640-138">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="39640-139">Описывает взаимодействие <xref:System.Data.DataSet> с XML-данными в качестве источника данных, включая загрузку и сохранение содержимого <xref:System.Data.DataSet> в виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="39640-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="39640-140">Потребление набора данных из веб-службы XML</span><span class="sxs-lookup"><span data-stu-id="39640-140">Consuming a DataSet from an XML Web Service</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="39640-141">Описывает создание веб-службы с поддержкой XML, использующей <xref:System.Data.DataSet> для передачи данных.</span><span class="sxs-lookup"><span data-stu-id="39640-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="39640-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="39640-142">Related Sections</span></span>  
 [<span data-ttu-id="39640-143">Новые возможности в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="39640-143">What's New in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="39640-144">Представляет новые возможности ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="39640-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="39640-145">Общие сведения о ADO.NET</span><span class="sxs-lookup"><span data-stu-id="39640-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="39640-146">Содержит введение в структуру и компоненты ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="39640-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="39640-147">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="39640-147">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="39640-148">Описывается загрузка **DataSet** данными из источника данных.</span><span class="sxs-lookup"><span data-stu-id="39640-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="39640-149">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="39640-149">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="39640-150">Описывается решение по внесению измененных в **DataSet** данных обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="39640-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="39640-151">Добавление существующих ограничений к набору данных</span><span class="sxs-lookup"><span data-stu-id="39640-151">Adding Existing Constraints to a DataSet</span></span>](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="39640-152">Описывает заполнение **DataSet** сведениями о первичном ключе из источника данных.</span><span class="sxs-lookup"><span data-stu-id="39640-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39640-153">См. также</span><span class="sxs-lookup"><span data-stu-id="39640-153">See also</span></span>

- [<span data-ttu-id="39640-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="39640-154">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="39640-155">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="39640-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
