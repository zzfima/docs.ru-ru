---
title: Ввод данных с помощью элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: 3ebfcaaf22ca632e5784dc1f01a351583e78e865
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090710"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d4892-102">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d4892-103">`DataGridView` Управления предоставляет несколько функций, позволяющих настраивать способ добавления или изменения данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d4892-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="d4892-104">Например ввод данных можно повысить эффективность, путем задания значений по умолчанию для новых строк и уведомления пользователей о при возникновении ошибок.</span><span class="sxs-lookup"><span data-stu-id="d4892-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4892-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d4892-105">In This Section</span></span>  
 [<span data-ttu-id="d4892-106">Практическое руководство. Определение режима редактирования для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4892-107">В этой статье описывается изменение способа пользователям начать редактирование ячейки.</span><span class="sxs-lookup"><span data-stu-id="d4892-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="d4892-108">Практическое руководство. Определение значения по умолчанию для новых строк в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="d4892-109">Описывает способ предварительного заполнения строк для новых записей сэкономить время ввода данных.</span><span class="sxs-lookup"><span data-stu-id="d4892-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="d4892-110">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4892-111">Описание строки для новых записей, в том числе сведения по скрытию, настройки его внешнего вида, и его связь с <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d4892-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="d4892-112">Пошаговое руководство: Проверка данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4892-113">Описание способов проверки пользовательского ввода для предотвращения ошибок форматирования ввода данных.</span><span class="sxs-lookup"><span data-stu-id="d4892-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="d4892-114">Пошаговое руководство: Обработка ошибок, возникающих во время ввода данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="d4892-115">Описывает способ обработки ошибок ввода данных, поступающих из источника данных, когда пользователь пытается зафиксировать новое значение.</span><span class="sxs-lookup"><span data-stu-id="d4892-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d4892-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="d4892-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d4892-117">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d4892-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d4892-118">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.EditMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d4892-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="d4892-119">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.</span><span class="sxs-lookup"><span data-stu-id="d4892-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="d4892-120">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.DataError> событий.</span><span class="sxs-lookup"><span data-stu-id="d4892-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="d4892-121">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.CellValidating> событий.</span><span class="sxs-lookup"><span data-stu-id="d4892-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4892-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d4892-122">Related Sections</span></span>  
 [<span data-ttu-id="d4892-123">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4892-124">Разделы, описывающие заполнение элемента управления данными вручную или из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="d4892-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4892-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d4892-125">See also</span></span>

- [<span data-ttu-id="d4892-126">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="d4892-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d4892-127">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4892-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
