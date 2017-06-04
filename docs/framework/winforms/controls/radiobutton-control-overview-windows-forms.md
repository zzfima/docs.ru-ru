---
title: "Общие сведения об элементе управления RadioButton (Windows Forms) | Microsoft Docs"
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
  - "RadioButton"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "переключатели, сведения о переключателях"
  - "переключатели, определение состояния"
  - "RadioButton - элемент управления [Windows Forms], об элементе управления RadioButton"
  - "RadioButton - элемент управления [Windows Forms], определение состояния"
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения об элементе управления RadioButton (Windows Forms)
Элементы управления Windows Forms <xref:System.Windows.Forms.RadioButton> \(переключатели\) обеспечивают выбор из двух или более взаимоисключающих вариантов.  Функции переключателей и флажков могут показаться схожими, но между ними есть важное отличие: в случае переключателя пользователь может выбрать лишь один вариант.  Напротив, флажков можно выбрать любое количество.  Определяя группу значений переключателя, разработчик формы предлагает пользователю набор вариантов, из которых может быть задан один и только один.  
  
## Использование элемента управления  
 При щелчке элемента управления <xref:System.Windows.Forms.RadioButton>, его свойству <xref:System.Windows.Forms.RadioButton.Checked%2A> задается значение `true` и вызывается обработчик событий <xref:System.Windows.Forms.Control.Click>.  При изменении значения свойства <xref:System.Windows.Forms.RadioButton.Checked%2A> происходит событие <xref:System.Windows.Forms.RadioButton.CheckedChanged>.  Если свойство <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> имеет значение `true` \(принимается по умолчанию\), то при выборе одного значения переключателя остальные значения группы автоматически сбрасываются.  Обычно этому свойству присваивают значение `false` только в тех случаях, когда в коде предусмотрена проверка допустимости выбранного варианта переключателя.  Текст, связанный с этим элементом управления, задается свойством <xref:System.Windows.Forms.Control.Text%2A>, которое также может определять клавиши быстрого доступа.  Клавиша доступа позволяет пользователю щелкнуть другой элемент управления, используя сочетание клавиши ALT и заданной клавиши.  Дополнительные сведения см. в разделах [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) и [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Элемент управления <xref:System.Windows.Forms.RadioButton> может выглядеть как кнопка команды, которая отображается как нажатая при выбранном значении переключателя, если свойство <xref:System.Windows.Forms.RadioButton.Appearance%2A> имеет значение <xref:System.Windows.Forms.Appearance>.  В переключателях можно также отображать рисунки с помощью свойств <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A>.  Дополнительные сведения см. в разделе [Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.RadioButton>   
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)   
 [Элемент управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)