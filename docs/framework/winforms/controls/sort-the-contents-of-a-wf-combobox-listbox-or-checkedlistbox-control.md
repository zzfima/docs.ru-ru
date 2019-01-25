---
title: Как выполнить Сортировка содержимого элемента Windows Forms ComboBox, ListBox или элементе управления CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 97965dcef1541aec51ba57a7cf314730f892f141
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686326"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Как выполнить Сортировка содержимого элемента Windows Forms ComboBox, ListBox или элементе управления CheckedListBox
Элементы управления Windows Forms не выполняют сортировку, когда они привязкой к данным. Чтобы отобразить отсортированные данные, использовать источник данных, который поддерживает сортировку и затем у источника данных, которые сортируют их. Источники данных, поддерживающих сортировку представления данных, диспетчеры представлений данных и массивы с сортировкой.  
  
 Если элемент управления не является привязкой к данным, можно сортировать его.  
  
### <a name="to-sort-the-list"></a>Чтобы отсортировать список  
  
1.  Задайте для свойства `Sorted` значение `true`.  
  
     Этот параметр перемещает все существующие элементы списка в отсортированном порядке.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Привязка данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [Практическое руководство. Добавление и удаление элементов Windows Forms ComboBox, ListBox или элементе управления CheckedListBox](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)
- [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
