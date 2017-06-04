---
title: "Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "CheckedListBox - элемент управления [Windows Forms], сортировка"
  - "поля со списком, сортировка содержимого"
  - "ComboBox - элемент управления [Windows Forms], сортировка содержимого"
  - "списки, сортировка содержимого"
  - "ListBox - элемент управления [Windows Forms], сортировка содержимого"
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms
Элементы управления Windows Forms не выполняют сортировку, если они привязаны к данным.  Чтобы вывести отсортированные данные, используйте источник данных, поддерживающий сортировку данных, и выполните ее с его помощью.  К источникам данных, поддерживающим сортировку, относятся представления данных, диспетчеры представлений данных и массивы с сортировкой.  
  
 Сортировка возможна, если элемент управления не привязан к данным.  
  
### Сортировка списка  
  
1.  Свойству `Sorted`  присвойте значение `true`.  
  
     Все существующие элементы списка выстроятся по порядку.  
  
## См. также  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)