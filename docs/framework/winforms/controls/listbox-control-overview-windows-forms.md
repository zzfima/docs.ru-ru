---
title: Общие сведения об элементе управления ListBox (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: d4cb423a6f32778695abeae725da9755b610d209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537568"
---
# <a name="listbox-control-overview-windows-forms"></a>Общие сведения об элементе управления ListBox (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListBox> элемент управления отображает список, из которого пользователь может выбрать один или несколько элементов. Если общее количество элементов превышает число, которое может быть отображено, полоса прокрутки автоматически добавляется <xref:System.Windows.Forms.ListBox> элемента управления. Когда <xref:System.Windows.Forms.ListBox.MultiColumn%2A> свойству `true`, элементы списка отображаются в нескольких столбцах и появляется горизонтальная полоса прокрутки. Когда <xref:System.Windows.Forms.ListBox.MultiColumn%2A> свойству `false`, элементы списка отображаются в одном столбце и появляется вертикальная полоса прокрутки. Когда <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> равно `true`, появляется полоса прокрутки независимо от количества элементов. <xref:System.Windows.Forms.ListBox.SelectionMode%2A> Свойство определяет, сколько элементов списка можно выбрать одновременно.  
  
## <a name="ways-to-change-the-listbox-control"></a>Способы изменения элемента управления ListBox  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Свойство возвращает целочисленное значение, соответствующее первому элементу выбранного в поле со списком. Можно программно изменить выбранный элемент, изменив <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значения в коде; соответствующий элемент в списке будет выделен в форме Windows Forms. Если элемент не выбран, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение-1. Если выбран первый элемент в списке, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение равно 0. Если выбрано несколько элементов, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение отражает выбранный элемент, который отображается первым в списке. <xref:System.Windows.Forms.ListBox.SelectedItem%2A> Свойства аналогичен <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, но возвращает сам элемент обычно строковое значение. <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Свойство отражает количество элементов в списке, а значение <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> свойство всегда имеет один больше, чем наибольшее возможное <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> поскольку <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> начинается с нуля.  
  
 Чтобы добавить или удалить элементы в <xref:System.Windows.Forms.ListBox> управления, используйте <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> метод. Кроме того, можно добавить элементы в список с помощью <xref:System.Windows.Forms.ListBox.Items%2A> во время разработки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListBox>  
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Общие сведения об элементе управления ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [Общие сведения об элементе управления CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
