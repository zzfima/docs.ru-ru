---
title: Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 4db1c133aabe39232a891183356e9c1b712f5cc8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150609"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="7a812-102">Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a812-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="7a812-103">Элементы управления Windows Forms не выполняют сортировку, когда они привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="7a812-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="7a812-104">Чтобы отобразить отсортированные данные, использовать источник данных, который поддерживает сортировку и затем у источника данных, которые сортируют их.</span><span class="sxs-lookup"><span data-stu-id="7a812-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="7a812-105">Источники данных, поддерживающих сортировку представления данных, диспетчеры представлений данных и массивы с сортировкой.</span><span class="sxs-lookup"><span data-stu-id="7a812-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="7a812-106">Если элемент управления не является привязкой к данным, можно сортировать его.</span><span class="sxs-lookup"><span data-stu-id="7a812-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="7a812-107">Чтобы отсортировать список</span><span class="sxs-lookup"><span data-stu-id="7a812-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="7a812-108">Задайте для свойства `Sorted` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7a812-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="7a812-109">Этот параметр перемещает все существующие элементы списка в отсортированном порядке.</span><span class="sxs-lookup"><span data-stu-id="7a812-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a812-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7a812-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="7a812-111">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a812-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="7a812-112">Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a812-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="7a812-113">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a812-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="7a812-114">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a812-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
