---
title: Практическое руководство. Сортировка содержимого элемента Windows Forms ComboBox, ListBox или элементе управления CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 4c00e853299c6eea2c97adb7f94cd7753ffa3d93
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705276"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Практическое руководство. Сортировка содержимого элемента Windows Forms ComboBox, ListBox или элементе управления CheckedListBox
Элементы управления Windows Forms не выполняют сортировку, когда они привязкой к данным. Чтобы отобразить отсортированные данные, использовать источник данных, который поддерживает сортировку и затем у источника данных, которые сортируют их. Источники данных, поддерживающих сортировку представления данных, диспетчеры представлений данных и массивы с сортировкой.  
  
 Если элемент управления не является привязкой к данным, можно сортировать его.  
  
### <a name="to-sort-the-list"></a>Чтобы отсортировать список  
  
1.  Задайте для свойства `Sorted` значение `true`.  
  
     Этот параметр перемещает все существующие элементы списка в отсортированном порядке.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
- [Практическое руководство. Добавление и удаление элементов Windows Forms ComboBox, ListBox или элементе управления CheckedListBox](add-and-remove-items-from-a-wf-combobox.md)
- [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
