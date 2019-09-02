---
title: Объекты DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: f362e4807bce4fb0e3e8c9ae8cdd6b4704fc28aa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203803"
---
# <a name="dataviews"></a><span data-ttu-id="3d6bd-102">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-102">DataViews</span></span>
<span data-ttu-id="3d6bd-103"><xref:System.Data.DataView> позволяет создавать различные представления данных, которые хранятся в <xref:System.Data.DataTable>. Эта возможность часто используется в приложениях связывания данных.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="3d6bd-104">С помощью **DataView**можно предоставлять данные в таблице с различными порядками сортировки, а данные можно фильтровать по состоянию строки или по критерию фильтра.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="3d6bd-105">Объект **DataView** обеспечивает динамическое представление данных в базовом **объекте DataTable**: содержимое, упорядочение и членство отображают изменения по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="3d6bd-106">Это поведение отличается от метода **SELECT** объекта **DataTable**, <xref:System.Data.DataRow> который возвращает массив из таблицы на основе определенного фильтра и (или) порядка сортировки: это содержимое отражает изменения в базовой таблице, но его членство и Упорядочивание остается статическим.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: this content reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="3d6bd-107">Динамические возможности **DataView** делают его идеальным для приложений привязки данных.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="3d6bd-108">Объект **DataView** предоставляет динамическое представление одного набора данных, похожее на представление базы данных, к которому можно применить различные критерии сортировки и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="3d6bd-109">Однако в отличие от представления базы данных, **DataView** не может рассматриваться как таблица и не может предоставлять представление соединяемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="3d6bd-110">Кроме того, нельзя исключать столбцы, существующие в исходной таблице, добавлять столбцы (например, вычисляемые), которых нет в исходной таблице.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="3d6bd-111">Можно использовать <xref:System.Data.DataView.DataViewManager%2A> для управления параметрами представления для всех таблиц в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="3d6bd-112">**DataViewManager** предоставляет удобный способ управления параметрами представления по умолчанию для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="3d6bd-113">При привязке элемента управления к более чем одной таблице **набора данных**привязка к **DataViewManager** является идеальным выбором.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d6bd-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3d6bd-114">In This Section</span></span>  
 [<span data-ttu-id="3d6bd-115">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-115">Creating a DataView</span></span>](creating-a-dataview.md)  
 <span data-ttu-id="3d6bd-116">Описывает создание **объекта DataView** для **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="3d6bd-117">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="3d6bd-117">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)  
 <span data-ttu-id="3d6bd-118">Описывает, как задать свойства **DataView** для возвращения подмножеств строк данных, отвечающих определенным условиям фильтра, или для возврата данных в определенном порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="3d6bd-119">Объекты DataRow и DataRowView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-119">DataRows and DataRowViews</span></span>](datarows-and-datarowviews.md)  
 <span data-ttu-id="3d6bd-120">Описывает, как получить доступ к данным, предоставляемым **DataView**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="3d6bd-121">Поиск строк</span><span class="sxs-lookup"><span data-stu-id="3d6bd-121">Finding Rows</span></span>](finding-rows.md)  
 <span data-ttu-id="3d6bd-122">Описывает, как найти определенную строку в **объекте DataView**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="3d6bd-123">ChildView и отношения</span><span class="sxs-lookup"><span data-stu-id="3d6bd-123">ChildViews and Relations</span></span>](childviews-and-relations.md)  
 <span data-ttu-id="3d6bd-124">Описывает создание представлений данных из связи типа «родители-потомки» с помощью **объекта DataView**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="3d6bd-125">Изменение объектов DataView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-125">Modifying DataViews</span></span>](modifying-dataviews.md)  
 <span data-ttu-id="3d6bd-126">Описывает, как изменить данные в базовой **таблице** данных с помощью **DataView**, включая включение или отключение обновлений.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="3d6bd-127">Обработка событий DataView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-127">Handling DataView Events</span></span>](handling-dataview-events.md)  
 <span data-ttu-id="3d6bd-128">Описывает, как использовать событие **ListChanged** для получения уведомлений при обновлении содержимого или порядка **представления DataView** .</span><span class="sxs-lookup"><span data-stu-id="3d6bd-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="3d6bd-129">Управление объектами DataView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-129">Managing DataViews</span></span>](managing-dataviews.md)  
 <span data-ttu-id="3d6bd-130">Описывает использование **DataViewManager** для управления параметрами **DataView** для каждой таблицы в **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3d6bd-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3d6bd-131">Related Sections</span></span>  
 <span data-ttu-id="3d6bd-132">[Веб-приложения ASP.NET](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3d6bd-132">[ASP.NET Web Applications](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span></span>  
 <span data-ttu-id="3d6bd-133">Описывает обзоры и подробные пошаговые инструкции по созданию приложений ASP.NET, Web Forms и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 <span data-ttu-id="3d6bd-134">[Приложения Windows](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3d6bd-134">[Windows Applications](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span></span>  
 <span data-ttu-id="3d6bd-135">Содержит подробные сведения о работе с консольными приложениями и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="3d6bd-136">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="3d6bd-136">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="3d6bd-137">Описывает объект **DataSet** и способы его использования для управления данными приложения.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="3d6bd-138">DataTables</span><span class="sxs-lookup"><span data-stu-id="3d6bd-138">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="3d6bd-139">Описывает объект **DataTable** и способ его использования для управления данными приложения самостоятельно или в составе **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="3d6bd-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3d6bd-140">ADO.NET</span></span>](../index.md)  
 <span data-ttu-id="3d6bd-141">Описывает архитектуру и компоненты ADO.NET, а также использование ADO.NET для доступа к существующим источникам данных и управления данными приложений.</span><span class="sxs-lookup"><span data-stu-id="3d6bd-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6bd-142">См. также</span><span class="sxs-lookup"><span data-stu-id="3d6bd-142">See also</span></span>

- [<span data-ttu-id="3d6bd-143">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3d6bd-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
