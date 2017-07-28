---
title: "Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms | Microsoft Docs"
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
  - "элементы управления [Windows Forms], группирование"
  - "переключатели, группирование"
  - "RadioButton - элемент управления [Windows Forms], группирование"
  - "элементы управления Windows Forms, группирование"
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms
Элементы управления Windows Forms <xref:System.Windows.Forms.RadioButton> служат для выбора между двумя или несколькими параметрами, из которых только один может быть присвоен процедуре или объекту.  Например, группа элементов управления <xref:System.Windows.Forms.RadioButton> может отображать выбор способа доставки заказа, но может быть использован только один способ.  Поэтому существует возможность выбора только одного элемента <xref:System.Windows.Forms.RadioButton>, даже если он является частью функциональной группы.  
  
 Переключатели группируются путем их рисования внутри таких контейнеров, как элемент управления <xref:System.Windows.Forms.Panel>, элемент управления <xref:System.Windows.Forms.GroupBox> или форма.  Все переключатели, добавленные непосредственно в форму, находятся в одной группе.  Для добавления отдельных групп следует разместить их внутри элементов управления или групп.  Дополнительные сведения о панелях и группах см. в разделах [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) и [Общие сведения об элементе управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).  
  
### Чтобы сгруппировать элементы управления RadioButton как набор для функционирования независимо от других наборов, выполните следующие действия.  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel> из **области элементов** **Windows Forms** в форму.  
  
2.  Нарисуйте элементы управления <xref:System.Windows.Forms.RadioButton> в <xref:System.Windows.Forms.GroupBox> или <xref:System.Windows.Forms.Panel>.  
  
## См. также  
 <xref:System.Windows.Forms.RadioButton>   
 [Общие сведения об элементе управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Элемент управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)