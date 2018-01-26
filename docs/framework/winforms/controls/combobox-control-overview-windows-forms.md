---
title: "Общие сведения об элементе управления ComboBox (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 801ebb97c6ee52ce52bbb8f96a07d55e68ca6f1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="combobox-control-overview-windows-forms"></a>Общие сведения об элементе управления ComboBox (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ComboBox> элемент управления используется для отображения данных в раскрывающемся поле со списком. По умолчанию <xref:System.Windows.Forms.ComboBox> элемент управления состоит из двух частей: верхняя часть представляет собой текстовое поле, которое пользователь может ввести элемент списка. Вторая часть представляет собой список, отображающий список элементов, из которых пользователь может выбрать один. Дополнительные сведения о других стилях поле со списком. в разделе [использование Windows Forms ComboBox Instead of ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> Свойство возвращает целочисленное значение, соответствующее выбранному элементу списка. Можно программно изменить выбранный элемент, изменив <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> значения в коде; соответствующий элемент в списке будет отображаться в текстового поля со списком. Если элемент не выбран, <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> значение-1. Если выбран первый элемент в списке, а затем <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> значение равно 0. <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> Свойства аналогичен <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , но возвращает сам элемент обычно строковое значение. <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> Свойство отражает количество элементов в списке, а значение <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> свойство всегда имеет один больше, чем наибольшее возможное <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> поскольку <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> начинается с нуля.  
  
 Чтобы добавить или удалить элементы в <xref:System.Windows.Forms.ComboBox> управления, используйте <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> метод. Кроме того, можно добавить элементы в список с помощью <xref:System.Windows.Forms.ComboBox.Items%2A> свойств в конструкторе.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ComboBox>  
 [Общие сведения об элементе управления ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Практическое руководство. Получение доступа к определенным элементам в элементах управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
