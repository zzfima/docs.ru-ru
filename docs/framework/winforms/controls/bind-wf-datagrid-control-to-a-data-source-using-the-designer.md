---
title: Привязка элемента управления DataGrid к источнику данных с помощью конструктора
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: cc0a74eca40e34f06b065980d25d922b919b0c3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744086"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="cab8c-102">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="cab8c-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="cab8c-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="cab8c-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="cab8c-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="cab8c-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="cab8c-105">Элемент управления Windows Forms <xref:System.Windows.Forms.DataGrid> специально разработан для вывода информации из источника данных.</span><span class="sxs-lookup"><span data-stu-id="cab8c-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="cab8c-106">Элемент управления привязывается во время разработки путем задания свойств <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> или во время выполнения путем вызова метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="cab8c-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="cab8c-107">Несмотря на то, что можно отображать данные из различных источников данных, наиболее типичными источниками являются наборы данных и представления.</span><span class="sxs-lookup"><span data-stu-id="cab8c-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>

 <span data-ttu-id="cab8c-108">Если источник данных доступен во время разработки, например, если форма содержит экземпляр набора данных или представление данных, можно привязать сетку к источнику данных во время разработки.</span><span class="sxs-lookup"><span data-stu-id="cab8c-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="cab8c-109">Затем можно просмотреть, как будут выглядеть данные в сетке.</span><span class="sxs-lookup"><span data-stu-id="cab8c-109">You can then preview what the data will look like in the grid.</span></span>

 <span data-ttu-id="cab8c-110">Можно также выполнить привязку сетки программным способом во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cab8c-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="cab8c-111">Это полезно, если необходимо задать источник данных на основе сведений, получаемых во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cab8c-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="cab8c-112">Например, приложение может позволить пользователю указать имя таблицы для просмотра.</span><span class="sxs-lookup"><span data-stu-id="cab8c-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="cab8c-113">Это также необходимо в ситуациях, когда источник данных не существует во время разработки.</span><span class="sxs-lookup"><span data-stu-id="cab8c-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="cab8c-114">К ним относятся такие источники данных, как массивы, коллекции, нетипизированные DataSet и модули чтения данных.</span><span class="sxs-lookup"><span data-stu-id="cab8c-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>

 <span data-ttu-id="cab8c-115">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="cab8c-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="cab8c-116">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cab8c-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="cab8c-117">В Visual Studio 2005 элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится на **панели элементов** .</span><span class="sxs-lookup"><span data-stu-id="cab8c-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="cab8c-118">Дополнительные сведения о добавлении элементов см. в разделе [как добавить элементы на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cab8c-118">For information about adding it, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="cab8c-119">Кроме того, в Visual Studio 2005 можно использовать окно **Источники данных** для привязки данных во время разработки.</span><span class="sxs-lookup"><span data-stu-id="cab8c-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="cab8c-120">Дополнительные сведения см. [в разделе Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="cab8c-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="cab8c-121">Привязка данных элемента управления DataGrid к одной таблице в конструкторе</span><span class="sxs-lookup"><span data-stu-id="cab8c-121">To data-bind the DataGrid control to a single table in the designer</span></span>

1. <span data-ttu-id="cab8c-122">Задайте для свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> элемента управления объект, содержащий элементы данных, к которым необходимо выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="cab8c-122">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="cab8c-123">Если источник данных является набором данных, задайте для свойства <xref:System.Windows.Forms.DataGrid.DataMember%2A> имя таблицы, к которой выполняется привязка.</span><span class="sxs-lookup"><span data-stu-id="cab8c-123">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>

3. <span data-ttu-id="cab8c-124">Если источник данных является набором данных или представлением данных, основанным на таблице набора данных, добавьте в форму код для заполнения набора данных.</span><span class="sxs-lookup"><span data-stu-id="cab8c-124">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>

     <span data-ttu-id="cab8c-125">Точный код, который вы используете, зависит от того, где набор данных получает данные.</span><span class="sxs-lookup"><span data-stu-id="cab8c-125">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="cab8c-126">Если набор данных заполняется непосредственно из базы данных, обычно вызывается метод `Fill` адаптера данных, как показано в следующем примере кода, который заполняет набор данных с именем `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="cab8c-126">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. <span data-ttu-id="cab8c-127">Используемых Добавьте соответствующие стили таблиц и столбцов в сетку.</span><span class="sxs-lookup"><span data-stu-id="cab8c-127">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>

     <span data-ttu-id="cab8c-128">Если стили таблиц отсутствуют, вы увидите таблицу, но с минимальным форматированием и отображением всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="cab8c-128">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="cab8c-129">Привязка элемента управления DataGrid к нескольким таблицам в наборе данных в конструкторе</span><span class="sxs-lookup"><span data-stu-id="cab8c-129">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>

1. <span data-ttu-id="cab8c-130">Задайте для свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> элемента управления объект, содержащий элементы данных, к которым необходимо выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="cab8c-130">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="cab8c-131">Если набор данных содержит связанные таблицы (то есть, если он содержит объект связи), задайте для свойства <xref:System.Windows.Forms.DataGrid.DataMember%2A> имя родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="cab8c-131">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>

3. <span data-ttu-id="cab8c-132">Напишите код для заполнения набора данных.</span><span class="sxs-lookup"><span data-stu-id="cab8c-132">Write code to fill the dataset.</span></span>

## <a name="see-also"></a><span data-ttu-id="cab8c-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cab8c-133">See also</span></span>

- [<span data-ttu-id="cab8c-134">Общие сведения об элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="cab8c-134">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="cab8c-135">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cab8c-135">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="cab8c-136">Элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="cab8c-136">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="cab8c-137">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cab8c-137">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="cab8c-138">Доступ к данным в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cab8c-138">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
