---
title: "Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e43a23d632b397889721373471a8fa165052d7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="c17a0-102">Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c17a0-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="c17a0-103">Элементы управления Windows Forms не сортировку, если они связаны с данными.</span><span class="sxs-lookup"><span data-stu-id="c17a0-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="c17a0-104">Чтобы отобразить отсортированные данные, использовать источник данных, поддерживающий сортировку и получится его сортировки источника данных.</span><span class="sxs-lookup"><span data-stu-id="c17a0-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="c17a0-105">Источники данных, поддерживающих сортировку представления данных, диспетчеры представлений данных и массивы с сортировкой.</span><span class="sxs-lookup"><span data-stu-id="c17a0-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="c17a0-106">Если элемент управления не имеет привязки к данным, то можно отсортировать.</span><span class="sxs-lookup"><span data-stu-id="c17a0-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="c17a0-107">Чтобы отсортировать список</span><span class="sxs-lookup"><span data-stu-id="c17a0-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="c17a0-108">Задайте для свойства `Sorted` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c17a0-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="c17a0-109">Этот параметр изменяет положение всех существующих элементов списка в порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="c17a0-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17a0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c17a0-110">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="c17a0-111">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c17a0-111">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="c17a0-112">Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c17a0-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="c17a0-113">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c17a0-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="c17a0-114">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c17a0-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
