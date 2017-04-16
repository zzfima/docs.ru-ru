---
title: "Общие сведения об элементе управления ComboBox (Windows Forms) | Microsoft Docs"
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
  - "ComboBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "поля со списком, сведения о полях со списком"
  - "ComboBox - элемент управления [Windows Forms], сведения об элементе управления ComboBox"
  - "раскрывающиеся списки, ComboBox - элемент управления"
  - "раскрывающиеся списки, Windows Forms"
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения об элементе управления ComboBox (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.ComboBox> используется для вывода данных в раскрывающемся поле со списком.  По умолчанию элемент управления <xref:System.Windows.Forms.ComboBox> отображается в виде двух частей: верхняя часть представляет собой текстовое поле, в которое пользователь может ввести элемент списка.  Вторая часть представляет собой список элементов, один из которых пользователь может выбрать.  Дополнительные сведения о других стилях поля со списком см. в разделе [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 Свойство <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> возвращает целочисленное значение, соответствующее выбранному элементу списка.  Выбранный элемент можно изменить программными средствами, изменив в коде значение <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>; соответствующий элемент списка появится в текстовом поле поля со списком.  Если выбранных элементов нет, значение <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> равно \-1.  Если в списке выбран первый элемент, значение <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> равно 0.  Свойство <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> аналогично свойству <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, но возвращает сам элемент, обычно в виде строкового значения.  Свойство <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> отражает число элементов в списке, а значение свойства <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> всегда на единицу больше максимально возможного значения свойства <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, поскольку для свойства <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> индексация ведется от нуля.  
  
 Чтобы добавить или удалить элементы в элементе управления <xref:System.Windows.Forms.ComboBox>, используйте метод <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> или <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>.  Кроме того, можно добавить элементы в список с помощью свойства <xref:System.Windows.Forms.ComboBox.Items%2A> во время разработки.  
  
## См. также  
 <xref:System.Windows.Forms.ComboBox>   
 [Общие сведения об элементе управления ListBox](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Практическое руководство. Получение доступа к определенным элементам в элементах управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)   
 [Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)