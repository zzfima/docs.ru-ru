---
title: "Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c4a2886dae3aee147d80957874d0d98714c0ca5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms
<xref:System.Windows.Forms.ComboBox> И <xref:System.Windows.Forms.ListBox> элементы управления имеют аналогичные поведения, а в некоторых случаях они взаимозаменяемы. Бывают случаи, тем не менее, когда одно из них более удобным использовать для задачи.  
  
 Как правило поле со списком подходит, когда есть список возможных вариантов, и поле со списком подходит, если требуется ограничить данные, вводимые в списке. Поле со списком содержит текстовое поле, поэтому варианты, отсутствующие в списке могут быть введены в. Исключение возникает, когда <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойству <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. В этом случае элемент управления будет выбирать элемент при вводе первой буквой.  
  
 Кроме того поля со списком сэкономить место на форме. Поскольку полный список не отображается, пока пользователь не щелкнет стрелку вниз, поле со списком легко можно разместить на небольшом пространстве, где поле со списком не может поместиться. Исключение возникает, когда <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> свойству <xref:System.Windows.Forms.ComboBoxStyle.Simple>: отображается полный список, и поле со списком будет занимать больше места, чем поле со списком.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
