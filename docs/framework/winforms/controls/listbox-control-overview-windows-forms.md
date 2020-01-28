---
title: Общие сведения об элементе управления ListBox
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745180"
---
# <a name="listbox-control-overview-windows-forms"></a>Общие сведения об элементе управления ListBox (Windows Forms)
Элемент управления <xref:System.Windows.Forms.ListBox> Windows Forms отображает список, из которого пользователь может выбрать один или несколько элементов. Если общее число элементов превышает число, которое может быть отображено, то в элемент управления <xref:System.Windows.Forms.ListBox> автоматически добавляется полоса прокрутки. Если свойство <xref:System.Windows.Forms.ListBox.MultiColumn%2A> имеет значение `true`, в списке отображаются элементы нескольких столбцов и отображается горизонтальная полоса прокрутки. Если свойство <xref:System.Windows.Forms.ListBox.MultiColumn%2A> имеет значение `false`, то в списке отображаются элементы в одном столбце и отображается вертикальная полоса прокрутки. Если <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> имеет значение `true`, полоса прокрутки отображается независимо от числа элементов. Свойство <xref:System.Windows.Forms.ListBox.SelectionMode%2A> определяет, сколько элементов списка можно выбрать за раз.  
  
## <a name="ways-to-change-the-listbox-control"></a>Способы изменения элемента управления ListBox  
 Свойство <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> возвращает целочисленное значение, соответствующее первому выбранному элементу в списке. Вы можете программно изменить выбранный элемент, изменив значение <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> в коде. соответствующий элемент в списке будет отображаться в форме Windows Forms. Если элемент не выбран, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение равно-1. Если первый элемент в списке выбран, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение равно 0. Если выбрано несколько элементов, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение отражает выбранный элемент, который отображается первым в списке. Свойство <xref:System.Windows.Forms.ListBox.SelectedItem%2A> аналогично <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, но возвращает сам элемент, обычно строковое значение. Свойство <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> отражает количество элементов в списке, а значение свойства <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> всегда равно больше максимально возможного <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значения, так как <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> отсчитывается от нуля.  
  
 Чтобы добавить или удалить элементы в элементе управления <xref:System.Windows.Forms.ListBox>, используйте метод <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>. Кроме того, можно добавить элементы в список с помощью свойства <xref:System.Windows.Forms.ListBox.Items%2A> во время разработки.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ListBox>
- [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Общие сведения об элементе управления ComboBox](combobox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления CheckedListBox](checkedlistbox-control-overview-windows-forms.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
- [Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
