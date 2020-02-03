---
title: Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742965"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
Windows Forms элементы управления не сортируются, если они привязаны к данным. Чтобы отобразить отсортированные данные, используйте источник данных, поддерживающий сортировку, а затем разсортируйте его в источнике данных. Источники данных, поддерживающие сортировку, — это представления данных, диспетчеры представлений данных и отсортированные массивы.  
  
 Если элемент управления не привязан к данным, его можно отсортировать.  
  
### <a name="to-sort-the-list"></a>Сортировка списка  
  
1. Установите свойство `Sorted` в значение `true`.  
  
     Этот параметр перемещает все существующие элементы списка в отсортированном порядке.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
- [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
