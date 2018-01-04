---
title: "Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca34b5daff07b733ccf2bfb4269c11cff80c7549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="00ef9-102">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00ef9-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="00ef9-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="00ef9-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="00ef9-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="00ef9-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="00ef9-105">Может отображать данные в Windows Forms <xref:System.Windows.Forms.DataGrid> управления в таблицах и столбцах, создав **DataGridTableStyle** объектов и добавления их в **GridTableStylesCollection** объекта, имеющего доступ через <xref:System.Windows.Forms.DataGrid> элемента управления **TableStyles** свойство.</span><span class="sxs-lookup"><span data-stu-id="00ef9-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="00ef9-106">Каждая таблица отображается содержимое таблицы данных указывается в **DataGridTableStyle** объекта **MappingName** свойство.</span><span class="sxs-lookup"><span data-stu-id="00ef9-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="00ef9-107">По умолчанию стиля таблицы стили столбцов, не указано, отображаются все столбцы в этой таблице данных.</span><span class="sxs-lookup"><span data-stu-id="00ef9-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="00ef9-108">Вы можете ограничить отображаются столбцы из таблицы, добавив **DataGridColumnStyle** объектов **GridColumnStylesCollection** объект, который можно получить с помощью  **GridColumnStyles** каждого экземпляра **DataGridTableStyle** объекта.</span><span class="sxs-lookup"><span data-stu-id="00ef9-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="00ef9-109">Добавление таблиц и столбцов в элемент управления DataGrid программными средствами</span><span class="sxs-lookup"><span data-stu-id="00ef9-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="00ef9-110">Для отображения данных в таблице, необходимо сначала привязать <xref:System.Windows.Forms.DataGrid> элемента управления к набору данных.</span><span class="sxs-lookup"><span data-stu-id="00ef9-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="00ef9-111">Дополнительные сведения см. в разделе [как: привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="00ef9-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="00ef9-112">Указывая программно стили столбцов всегда создавать **DataGridColumnStyle** объектов и добавлять их в **GridColumnStylesCollection** объекта перед добавлением  **DataGridTableStyle** объектов **GridTableStylesCollection** объекта.</span><span class="sxs-lookup"><span data-stu-id="00ef9-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="00ef9-113">При добавлении пустого **DataGridTableStyle** в коллекцию **DataGridColumnStyle** объекты создаются автоматически для вас.</span><span class="sxs-lookup"><span data-stu-id="00ef9-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="00ef9-114">Следовательно, будет создано исключение при попытке добавить новый **DataGridColumnStyle** объектов с повторяющимися **MappingName** значения **GridColumnStylesCollection**объекта.</span><span class="sxs-lookup"><span data-stu-id="00ef9-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2.  <span data-ttu-id="00ef9-115">Объявите новый стиль таблицы и присвойте ему имя сопоставления.</span><span class="sxs-lookup"><span data-stu-id="00ef9-115">Declare a new table style and set its mapping name.</span></span>  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  <span data-ttu-id="00ef9-116">Объявите новый стиль столбца и задайте его имя сопоставления и другие свойства.</span><span class="sxs-lookup"><span data-stu-id="00ef9-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  <span data-ttu-id="00ef9-117">Вызовите **добавить** метод **GridColumnStylesCollection** объект для добавления столбца таблицы стилей</span><span class="sxs-lookup"><span data-stu-id="00ef9-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  <span data-ttu-id="00ef9-118">Вызовите **добавить** метод **GridTableStylesCollection** объект для добавления стилей таблиц сетки данных.</span><span class="sxs-lookup"><span data-stu-id="00ef9-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="00ef9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="00ef9-119">See Also</span></span>  
 [<span data-ttu-id="00ef9-120">Элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="00ef9-120">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="00ef9-121">Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00ef9-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
