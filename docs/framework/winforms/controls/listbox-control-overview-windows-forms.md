---
title: Общие сведения об элементе управления ListBox (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 2bba90f704458e1c724328feccaaf6f04b98ecb4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723989"
---
# <a name="listbox-control-overview-windows-forms"></a>Общие сведения об элементе управления ListBox (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListBox> элемент управления отображает список, из которого пользователь может выбрать один или несколько элементов. Если общее количество элементов превышает номер, который может быть отображен, полосы прокрутки автоматически добавляется <xref:System.Windows.Forms.ListBox> элемента управления. Когда <xref:System.Windows.Forms.ListBox.MultiColumn%2A> свойству `true`, поле со списком элементы отображаются в нескольких столбцах и горизонтальную полосу прокрутки. Когда <xref:System.Windows.Forms.ListBox.MultiColumn%2A> свойству `false`, поле со списком элементы отображаются в одном столбце и вертикальную полосу прокрутки. Когда <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> присваивается `true`, полоса прокрутки отображается независимо от количества элементов. <xref:System.Windows.Forms.ListBox.SelectionMode%2A> Свойство определяет, сколько элементов списка можно выбрать одновременно.  
  
## <a name="ways-to-change-the-listbox-control"></a>Способы изменения элемента управления ListBox  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> Свойство возвращает целочисленное значение, соответствующее первый выбранный элемент в поле со списком. Можно программно изменить выбранный элемент, изменив <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение в коде; соответствующего элемента в списке будет выделен в форме Windows. Если элемент не выбран, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение равно -1. Если выбран первый элемент в списке, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение равно 0. Если выбрано несколько элементов, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> значение отражает выбранного элемента, занимающий первую позицию в списке. <xref:System.Windows.Forms.ListBox.SelectedItem%2A> Свойства аналогична <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, но возвращает сам элемент обычно строковое значение. <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> Свойство отражает количество элементов в списке, а значение <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> свойство всегда имеет один больше, чем наибольшее возможное <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> поскольку значение <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> начинается с нуля.  
  
 Для добавления или удаления элементов в <xref:System.Windows.Forms.ListBox> управления, используйте <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> метод. Кроме того, можно добавить элементы в список с помощью <xref:System.Windows.Forms.ListBox.Items%2A> во время разработки.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ListBox>
- [Практическое руководство. Добавление и удаление элементов Windows Forms ComboBox, ListBox или элементе управления CheckedListBox](add-and-remove-items-from-a-wf-combobox.md)
- [Практическое руководство. Сортировка содержимого элемента Windows Forms ComboBox, ListBox или элементе управления CheckedListBox](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Практическое руководство. Привязка к данным Windows Forms ComboBox или ListBox-элемент управления](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Общие сведения об элементе управления ComboBox](combobox-control-overview-windows-forms.md)
- [Общие сведения об элементе управления CheckedListBox](checkedlistbox-control-overview-windows-forms.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
- [Практическое руководство. Создание таблицы подстановки для Windows Forms ComboBox, ListBox или элементе управления CheckedListBox](create-a-lookup-table-for-a-wf-combobox-listbox.md)
