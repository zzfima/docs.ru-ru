---
title: Использование конструктора с элементом управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 50e8bddb97c2dfb84cebdbb2ca4d42a6c5743304
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728366"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="11120-102">Использование конструктора с элементом управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11120-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="11120-103">Visual Studio предоставляет поддержку конструктора для элемента управления `DataGridView`, который позволяет выполнять множество задач по настройке без написания кода.</span><span class="sxs-lookup"><span data-stu-id="11120-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="11120-104">Эти задачи включают привязку элемента управления к источнику данных, изменение столбцов, используемых для отображения данных, а также настройку внешнего вида и основного поведения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="11120-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11120-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="11120-105">In This Section</span></span>  
 [<span data-ttu-id="11120-106">Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-107">Описывает использование диалоговых окон **Добавление столбцов** и **Изменение столбцов** для заполнения и изменения коллекции Columns.</span><span class="sxs-lookup"><span data-stu-id="11120-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="11120-108">Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-109">Описывает, как использовать параметр **Выбор источника данных** в смарт-теге элемента управления для подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="11120-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="11120-110">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-111">Описывает, как использовать диалоговое окно **Изменение столбцов** для изменения порядка столбцов.</span><span class="sxs-lookup"><span data-stu-id="11120-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="11120-112">Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="11120-113">Описывает использование диалогового окна **Изменение столбцов** для изменения типов столбцов.</span><span class="sxs-lookup"><span data-stu-id="11120-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="11120-114">Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-115">Описывает, как использовать смарт-тег элемента управления, чтобы разрешить пользователям изменять порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="11120-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="11120-116">Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-117">Описывает использование диалогового окна **Изменение столбцов** для предотвращения прокрутки отдельных столбцов.</span><span class="sxs-lookup"><span data-stu-id="11120-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="11120-118">Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-119">Описывает использование диалогового окна **Изменение столбцов** для скрытия конкретных столбцов.</span><span class="sxs-lookup"><span data-stu-id="11120-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="11120-120">Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-121">Описывает, как использовать диалоговое окно **Изменение столбцов** , чтобы запретить пользователям изменять значения в конкретных столбцах.</span><span class="sxs-lookup"><span data-stu-id="11120-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="11120-122">Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-123">Описывает, как использовать смарт-тег элемента управления, чтобы запретить пользователям добавлять или удалять строки.</span><span class="sxs-lookup"><span data-stu-id="11120-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="11120-124">Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="11120-125">Описывает использование диалогового окна « **Построитель** полей» для создания внешнего вида, похожего на главную книгу, в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="11120-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="11120-126">Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="11120-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="11120-127">Описывает использование диалогового окна « **Построитель** полей» для настройки основного внешнего вида и форматов отображения данных для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="11120-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="11120-128">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="11120-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="11120-129">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="11120-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11120-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="11120-130">See also</span></span>

- [<span data-ttu-id="11120-131">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="11120-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
