---
title: Использование конструктора с элементом управления DataGridView Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 618e422c893d0f0c1870d5b9bf2360eb946dd3c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539829"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="1fecf-102">Использование конструктора с элементом управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fecf-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1fecf-103">Visual Studio обеспечивает поддержку конструктора для `DataGridView` элемент управления, который позволяет выполнять многие задачи установки без написания кода.</span><span class="sxs-lookup"><span data-stu-id="1fecf-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="1fecf-104">Эти задачи включают привязки элемента управления к источнику данных, изменение столбцов, используемый для отображения данных и настройка внешнего вида и поведение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1fecf-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fecf-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1fecf-105">In This Section</span></span>  
 [<span data-ttu-id="1fecf-106">Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-107">Описывает использование **Добавление столбцов** и **Правка столбцов** диалоговыми окнами для заполнения и изменения набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fecf-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="1fecf-108">Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-109">Описывает использование **Выбор источника данных** параметр смарт-теге элемента управления для подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="1fecf-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="1fecf-110">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-111">Описывает использование **Правка столбцов** диалогового окна для изменения порядка столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fecf-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="1fecf-112">Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="1fecf-113">Описывает использование **Правка столбцов** диалоговое окно «», чтобы изменить типы столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fecf-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="1fecf-114">Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-115">Описывает, как использовать смарт-тег элемента управления, чтобы разрешить пользователям изменять порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fecf-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="1fecf-116">Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-117">Описывает использование **Правка столбцов** диалогового окна для запрещения прокрутки определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fecf-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="1fecf-118">Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-119">Описывает использование **Правка столбцов** диалоговое окно «» для скрытия определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="1fecf-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="1fecf-120">Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-121">Описывает использование **Правка столбцов** диалоговое окно «», чтобы запретить пользователям изменять значения в определенных столбцах.</span><span class="sxs-lookup"><span data-stu-id="1fecf-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="1fecf-122">Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-123">Описывает, как использовать смарт-тег элемента управления, чтобы запретить пользователям добавлять или удалять строки.</span><span class="sxs-lookup"><span data-stu-id="1fecf-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="1fecf-124">Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="1fecf-125">Описывает использование **построитель стилей ячеек** диалоговое окно «» для создания внешнего вида, подобном бухгалтерским книгам: в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="1fecf-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="1fecf-126">Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="1fecf-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/default-cell-styles-datagridview.md)  
 <span data-ttu-id="1fecf-127">Описывает использование **построитель стилей ячеек** форматирует диалогового окна для настройки базового внешнего вида и отображения данных для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1fecf-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1fecf-128">Ссылка</span><span class="sxs-lookup"><span data-stu-id="1fecf-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="1fecf-129">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="1fecf-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fecf-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1fecf-130">See Also</span></span>  
 [<span data-ttu-id="1fecf-131">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="1fecf-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
