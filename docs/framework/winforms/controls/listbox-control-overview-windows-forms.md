---
title: "Общие сведения об элементе управления ListBox (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "списки, сведения о списках"
  - "ListBox - элемент управления [Windows Forms], об элементе управления ListBox"
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения об элементе управления ListBox (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.ListBox> отображает список элементов, в котором пользователь может выбрать один или несколько элементов.  Если не все элементы могут одновременно отобразиться в поле списка, к элементу управления <xref:System.Windows.Forms.ListBox> автоматически добавляется полоса прокрутки.  Если для свойства <xref:System.Windows.Forms.ListBox.MultiColumn%2A> задано значение `true`, элементы списка отображаются в нескольких столбцах и появляется горизонтальная полоса прокрутки.  Если для свойства <xref:System.Windows.Forms.ListBox.MultiColumn%2A> задано значение `false`, элементы списка отображаются в одном столбце и появляется вертикальная полоса прокрутки.  Если для <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> задано значение `true`, полоса прокрутки появляется независимо от числа элементов.  Свойство <xref:System.Windows.Forms.ListBox.SelectionMode%2A> определяет, сколько элементов списка можно выбрать одновременно.  
  
## Способы изменения элемента управления ListBox  
 Свойство <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> возвращает целочисленное значение, соответствующее первому выбранному элементу списка.  Выбранный элемент можно изменить программными средствами, изменив в коде значение <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>; соответствующий элемент списка будет выделен в форме Windows.  Если выбранных элементов нет, значение <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> равно \-1.  Если в списке выбран первый элемент, значение <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> равно 0.  Если выбрано несколько элементов, значение свойства <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> отражает выбранный элемент, появляющийся первым в списке.  Свойство <xref:System.Windows.Forms.ListBox.SelectedItem%2A> аналогично свойству <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, но возвращает сам элемент, обычно в виде строкового значения.  Свойство <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> отражает число элементов в списке, а значение свойства <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> всегда на единицу больше максимально возможного значения свойства <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, поскольку для свойства <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> индексация ведется от нуля.  
  
 Чтобы добавить или удалить элементы в элементе управления <xref:System.Windows.Forms.ListBox>, используйте метод <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>.  Кроме того, можно добавить элементы в список с помощью свойства <xref:System.Windows.Forms.ListBox.Items%2A> во время разработки.  
  
## См. также  
 <xref:System.Windows.Forms.ListBox>   
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [Общие сведения об элементе управления ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)