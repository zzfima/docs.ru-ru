---
title: "Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms | Microsoft Docs"
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
  - "элементы управления с привязкой, поля со списком"
  - "поля со списком, сравнение с обычными списками"
  - "ComboBox - элемент управления [Windows Forms], сравнение с ListBox"
  - "ListBox - элемент управления [Windows Forms], доступ к элементам"
  - "ListBox - элемент управления [Windows Forms], добавление и удаление элементов"
  - "ListBox - элемент управления [Windows Forms], в сравнении с ComboBox"
  - "ListCount - свойство"
  - "ListIndex - свойство"
  - "элементы управления Windows Forms, привязка данных"
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms
Поведение элементов управления <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> очень похоже, и в некоторых случаях они взаимозаменяемы.  Однако в других случаях какой\-либо из них в большей мере соответствует поставленной задаче.  
  
 Как правило, поле со списком используется при наличии списка возможных вариантов, а список — при необходимости ограничить данные, вводимые в список.  Поле со списком содержит текстовое поле, которое позволяет вручную вводить варианты, не представленные в списке.  Исключение возникает, когда свойству <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> присваивается значение <xref:System.Windows.Forms.ComboBoxStyle>.  В этом случае элемент управления будет выбирать соответствующий элемент из списка по первой введенной букве.  
  
 Кроме того, поля со списком экономят место в форме.  Поскольку полный список не отображается, пока пользователь не щелкнет кнопку со стрелкой вниз, поле со списком легко можно разместить на небольшом пространстве, на котором не поместился бы список.  Исключение составляет случай, когда для свойства <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> задано значение <xref:System.Windows.Forms.ComboBoxStyle>; при этом отображается полный список, и поле со списком занимает больше места, чем занял бы список.  
  
## См. также  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)