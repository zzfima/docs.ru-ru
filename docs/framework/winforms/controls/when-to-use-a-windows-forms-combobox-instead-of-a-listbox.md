---
title: ComboBox и ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739924"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms
<xref:System.Windows.Forms.ComboBox> и элементы управления <xref:System.Windows.Forms.ListBox> имеют похожие поведения, и в некоторых случаях они могут быть взаимозаменяемыми. Однако бывают ситуации, когда один из них более подходит для задачи.  
  
 Как правило, поле со списком подходит, если имеется список предлагаемых вариантов, и если необходимо ограничить входные данные на содержимое списка, то поле со списком подходит. Поле со списком содержит текстовое поле, поэтому варианты, отсутствующие в списке, можно вводить в. Исключением является то, что свойство <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> имеет значение <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. В этом случае элемент управления выберет элемент, если ввести его первую букву.  
  
 Кроме того, поля со списком сохраняют место в форме. Поскольку полный список не отображается до тех пор, пока пользователь не щелкнет стрелку вниз, поле со списком можно легко разместить в маленьком пространстве, в котором поле со списком не умещается. Исключением является то, что свойство <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> имеет значение <xref:System.Windows.Forms.ComboBoxStyle.Simple>: полный список отображается, а поле со списком занимает больше места, чем поле со списком.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
