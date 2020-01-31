---
title: Общие сведения об элементе управления ComboBox
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 9fb270d7787902872a32a87c140316f756bd48aa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743846"
---
# <a name="combobox-control-overview-windows-forms"></a>Общие сведения об элементе управления ComboBox (Windows Forms)
Элемент управления <xref:System.Windows.Forms.ComboBox> Windows Forms используется для вывода данных в раскрывающемся поле со списком. По умолчанию элемент управления <xref:System.Windows.Forms.ComboBox> отображается в двух частях: Верхняя часть — это текстовое поле, позволяющее пользователю ввести элемент списка. Вторая часть — это поле со списком, в котором отображается список элементов, из которых пользователь может выбрать один из них. Дополнительные сведения о других стилях поля со списком см. в разделе [когда следует использовать Windows Forms ComboBox вместо ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Свойство <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> возвращает целочисленное значение, соответствующее выбранному элементу списка. Вы можете программно изменить выбранный элемент, изменив значение <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> в коде. соответствующий элемент списка появится в текстовом поле поля со списком. Если элемент не выбран, <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> значение равно-1. Если выбран первый элемент в списке, <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> значение равно 0. Свойство <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> аналогично <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, но возвращает сам элемент, обычно строковое значение. Свойство <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> отражает количество элементов в списке, а значение свойства <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> всегда равно больше максимально возможного <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> значения, так как <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> отсчитывается от нуля.  
  
 Чтобы добавить или удалить элементы в элементе управления <xref:System.Windows.Forms.ComboBox>, используйте метод <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>. Кроме того, можно добавить элементы в список с помощью свойства <xref:System.Windows.Forms.ComboBox.Items%2A> в конструкторе.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ComboBox>
- [Общие сведения об элементе управления ListBox](listbox-control-overview-windows-forms.md)
- [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Практическое руководство. Получение доступа к определенным элементам в элементах управления ComboBox, ListBox или CheckedListBox в Windows Forms](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
- [Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
