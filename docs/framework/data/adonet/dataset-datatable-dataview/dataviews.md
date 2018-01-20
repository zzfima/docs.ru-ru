---
title: "Объекты DataView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a><span data-ttu-id="b26eb-102">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="b26eb-102">DataViews</span></span>
<span data-ttu-id="b26eb-103"><xref:System.Data.DataView> позволяет создавать различные представления данных, которые хранятся в <xref:System.Data.DataTable>. Эта возможность часто используется в приложениях связывания данных.</span><span class="sxs-lookup"><span data-stu-id="b26eb-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="b26eb-104">С помощью **DataView**, можно представить данные в таблице с различными порядками сортировки, и можно фильтровать данные по состоянию строки или на основе критерия фильтра.</span><span class="sxs-lookup"><span data-stu-id="b26eb-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="b26eb-105">Объект **DataView** обеспечивает динамическое представление данных в базовом **DataTable**: содержимое, упорядочение и членство отображают изменения по мере их возникновения.</span><span class="sxs-lookup"><span data-stu-id="b26eb-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="b26eb-106">Это поведение отличается от **выберите** метод **DataTable**, который возвращает <xref:System.Data.DataRow> массив из таблицы на основании определенного фильтра или порядка сортировки: thiscontent отражает изменения базовые таблицы, но при этом членство и упорядочение будут статическими.</span><span class="sxs-lookup"><span data-stu-id="b26eb-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: thiscontent reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="b26eb-107">Динамические возможности **DataView** идеально подходит для приложений привязки данных.</span><span class="sxs-lookup"><span data-stu-id="b26eb-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="b26eb-108">Объект **DataView** обеспечивает динамическое представление единого набора данных во многом похожего представления базы данных, к которому можно применить различные критерии сортировки и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b26eb-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="b26eb-109">В отличие от представления базы данных, однако **DataView** не может рассматриваться как таблицы и не может обеспечить представление соединяемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="b26eb-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="b26eb-110">Кроме того, нельзя исключать столбцы, существующие в исходной таблице, добавлять столбцы (например, вычисляемые), которых нет в исходной таблице.</span><span class="sxs-lookup"><span data-stu-id="b26eb-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="b26eb-111">Можно использовать <xref:System.Data.DataView.DataViewManager%2A> для управления настройками представления для всех таблиц в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="b26eb-112">**DataViewManager** предоставляет удобный способ для управления настройками представления по умолчанию для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="b26eb-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="b26eb-113">При привязке элемента управления к более чем одна таблица из **DataSet**привязка **DataViewManager** является идеальным выбором.</span><span class="sxs-lookup"><span data-stu-id="b26eb-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b26eb-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b26eb-114">In This Section</span></span>  
 [<span data-ttu-id="b26eb-115">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="b26eb-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="b26eb-116">Описывает создание **DataView** для **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="b26eb-117">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="b26eb-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="b26eb-118">Описывает, как задать свойства **DataView** для возврата подмножества строк данных, соответствующих определенным условиям фильтра, или для возвращения данных в определенном порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="b26eb-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="b26eb-119">Объекты DataRow и DataRowView</span><span class="sxs-lookup"><span data-stu-id="b26eb-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="b26eb-120">Описывает, как получить доступ к данным, предоставляемым **DataView**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="b26eb-121">Поиск строк</span><span class="sxs-lookup"><span data-stu-id="b26eb-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="b26eb-122">Описывает способ поиска определенной строки в **DataView**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="b26eb-123">ChildView и отношения</span><span class="sxs-lookup"><span data-stu-id="b26eb-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="b26eb-124">Описывает способ создания представлений данных из отношения родитель потомок с помощью **DataView**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="b26eb-125">Изменение объектов DataView</span><span class="sxs-lookup"><span data-stu-id="b26eb-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="b26eb-126">Содержит описание процесса изменения данных в базовом **DataTable** через **DataView**, в том числе включение и отключение обновлений.</span><span class="sxs-lookup"><span data-stu-id="b26eb-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="b26eb-127">Обработка событий DataView</span><span class="sxs-lookup"><span data-stu-id="b26eb-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="b26eb-128">Описывает использование **ListChanged** событий для получения уведомления при содержимого или порядка **DataView** обновляется.</span><span class="sxs-lookup"><span data-stu-id="b26eb-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="b26eb-129">Управление объектами DataView</span><span class="sxs-lookup"><span data-stu-id="b26eb-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="b26eb-130">Описывает использование **DataViewManager** для управления **DataView** параметры для каждой таблицы в **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b26eb-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b26eb-131">Related Sections</span></span>  
 [<span data-ttu-id="b26eb-132">Веб-приложений ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b26eb-132">ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 <span data-ttu-id="b26eb-133">Описывает обзоры и подробные пошаговые инструкции по созданию приложений ASP.NET, Web Forms и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="b26eb-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 [<span data-ttu-id="b26eb-134">Приложения Windows</span><span class="sxs-lookup"><span data-stu-id="b26eb-134">Windows Applications</span></span>](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 <span data-ttu-id="b26eb-135">Содержит подробные сведения о работе с консольными приложениями и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b26eb-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="b26eb-136">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="b26eb-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="b26eb-137">Описывает **DataSet** объекта и как ее можно использовать для управления данными приложения.</span><span class="sxs-lookup"><span data-stu-id="b26eb-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="b26eb-138">DataTables</span><span class="sxs-lookup"><span data-stu-id="b26eb-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="b26eb-139">Описывает **DataTable** объекта и как ее можно использовать для управления данными приложений самостоятельно или как часть **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b26eb-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="b26eb-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b26eb-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="b26eb-141">Описывает архитектуру и компоненты ADO.NET, а также использование ADO.NET для доступа к существующим источникам данных и управления данными приложений.</span><span class="sxs-lookup"><span data-stu-id="b26eb-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26eb-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b26eb-142">See Also</span></span>  
 [<span data-ttu-id="b26eb-143">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b26eb-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
