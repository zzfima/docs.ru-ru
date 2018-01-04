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
ms.workload: dotnet
ms.openlocfilehash: 4f266af44f954cb8416e1f7672f6642ab7c6995b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
Элементы управления Windows Forms не сортировку, если они связаны с данными. Чтобы отобразить отсортированные данные, использовать источник данных, поддерживающий сортировку и получится его сортировки источника данных. Источники данных, поддерживающих сортировку представления данных, диспетчеры представлений данных и массивы с сортировкой.  
  
 Если элемент управления не имеет привязки к данным, то можно отсортировать.  
  
### <a name="to-sort-the-list"></a>Чтобы отсортировать список  
  
1.  Задайте для свойства `Sorted` значение `true`.  
  
     Этот параметр изменяет положение всех существующих элементов списка в порядке сортировки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [Привязка данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
