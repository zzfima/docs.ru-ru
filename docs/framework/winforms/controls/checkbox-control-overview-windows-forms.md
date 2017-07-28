---
title: "Общие сведения об элементе управления CheckBox (Windows Forms) | Microsoft Docs"
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
  - "CheckBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления с привязкой, флажки"
  - "флажки, сведения о флажках"
  - "CheckBox - элемент управления [Windows Forms], сведения об элементе управления CheckBox"
  - "привязка данных, элементы управления CheckBox"
  - "элементы управления с привязкой к данным, флажки"
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Общие сведения об элементе управления CheckBox (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox> указывает, включено или отключено какое\-либо конкретное условие.  Обычно он используется для представления пользователю выбора типа "Да\/Нет" или "Истина\/Ложь".  Элементы управления типа "флажок" можно объединять в группы для предоставления пользователю нескольких вариантов выбора. В такой группе пользователь может установить один или несколько флажков.  
  
 Элементы управления "флажок" и "переключатель" сходны в том, что каждый используется для указания варианта, выбранного пользователем.  Их отличие заключается в том, что в группе переключателей можно выбрать только один элемент.  В группе флажков можно выбрать любое количество элементов.  
  
 Флажок можно подключить к элементам базы данных путем связывания данных.  Несколько флажков объединяются в группу с помощью элемента управления <xref:System.Windows.Forms.GroupBox>.  Это средство используется для простоты представления в структуре интерфейса пользователя, поскольку в конструкторе форм сгруппированные элементы управления можно перемещать одновременно.  Дополнительные сведения см. в разделах [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md) и [Элемент управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 Элемент управления <xref:System.Windows.Forms.CheckBox> имеет два важных свойства: <xref:System.Windows.Forms.CheckBox.Checked%2A> и <xref:System.Windows.Forms.CheckBox.CheckState%2A>.  Свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает `true` или `false`.  Свойство <xref:System.Windows.Forms.CheckBox.CheckState%2A> возвращает или <xref:System.Windows.Forms.CheckState>, или <xref:System.Windows.Forms.CheckState>; если же для свойства <xref:System.Windows.Forms.CheckBox.ThreeState%2A> установлено значение `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A>, это свойство может возвращать <xref:System.Windows.Forms.CheckState>.  При неопределенном состоянии поле флажка отображается затененным, что означает недоступность параметра.  
  
## См. также  
 <xref:System.Windows.Forms.CheckBox>   
 [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [Элемент управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)