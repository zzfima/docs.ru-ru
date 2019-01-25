---
title: Использование конструктора с элементом управления DataGridView Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 588db8b2f66bbfd58ea6197a7b5a65bb8ecbfd19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644823"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="4a48a-102">Использование конструктора с элементом управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a48a-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4a48a-103">Visual Studio предоставляет поддержку конструктора для `DataGridView` элемент управления, который позволяет выполнять множество задач установки без написания кода.</span><span class="sxs-lookup"><span data-stu-id="4a48a-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="4a48a-104">Эти задачи включают привязку элемента управления к источнику данных, изменение столбцов, используемый для отображения данных и изменив внешний вид и поведение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4a48a-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a48a-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4a48a-105">In This Section</span></span>  
 [<span data-ttu-id="4a48a-106">Практическое руководство. Добавлять и удалять столбцы в элементе управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-107">Описывает использование **Добавление столбцов** и **Правка столбцов** диалоговым окнам для заполнения и изменения набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a48a-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="4a48a-108">Практическое руководство. Привязка данных к элементу управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-109">Описывает использование **Выбор источника данных** параметр на смарт-теге элемента управления для подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="4a48a-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="4a48a-110">Практическое руководство. Изменить порядок столбцов в элементе управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-111">Описывает использование **Правка столбцов** диалоговое окно для изменения порядка столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a48a-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="4a48a-112">Практическое руководство. Изменение типа столбца DataGridView Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="4a48a-113">Описывает использование **Правка столбцов** диалоговое окно, чтобы изменить типы столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a48a-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="4a48a-114">Практическое руководство. Разрешение изменения порядка столбцов в элементе управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-115">В этой статье описывается использование смарт-тега элемента управления, чтобы пользователи могли изменять порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a48a-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="4a48a-116">Практическое руководство. Закрепление столбцов в элементе управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-117">Описывает использование **Правка столбцов** диалоговое окно, чтобы избежать прокрутки определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a48a-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="4a48a-118">Практическое руководство. Скрыть столбцы в элементе управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-119">Описывает использование **Правка столбцов** диалоговое окно, чтобы скрыть определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a48a-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="4a48a-120">Практическое руководство. Столбцы, сделайте доступным только для чтения в элементе управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-121">Описывает использование **Правка столбцов** диалоговое окно, чтобы запретить пользователям изменять значения в определенных столбцах.</span><span class="sxs-lookup"><span data-stu-id="4a48a-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="4a48a-122">Практическое руководство. Предотвращение добавления и удаления в элементе управления DataGridView формы Windows с помощью конструктора строк</span><span class="sxs-lookup"><span data-stu-id="4a48a-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-123">В этой статье описывается использование смарт-тега элемента управления, чтобы запретить пользователям добавлять или удалять строки.</span><span class="sxs-lookup"><span data-stu-id="4a48a-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="4a48a-124">Практическое руководство. Установка стилей чередующихся строк для элемента управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="4a48a-125">Описывает использование **построителя CellStyle** диалоговое окно для создания внешнего вида, подобном бухгалтерским книгам: в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4a48a-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="4a48a-126">Практическое руководство. Установка стилей ячейки по умолчанию и форматов данных для элемента управления DataGridView формы Windows с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4a48a-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/default-cell-styles-datagridview.md)  
 <span data-ttu-id="4a48a-127">Описывает использование **построителя CellStyle** диалоговое окно для настройки основного внешнего вида и отображения данных форматы для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4a48a-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4a48a-128">Ссылка</span><span class="sxs-lookup"><span data-stu-id="4a48a-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="4a48a-129">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4a48a-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a48a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4a48a-130">See also</span></span>
- [<span data-ttu-id="4a48a-131">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="4a48a-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
