---
title: "Общие сведения об элементе управления RadioButton (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ac0a04c506919ef807a3f8c5ed5aa75ee998f64a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="radiobutton-control-overview-windows-forms"></a>Общие сведения об элементе управления RadioButton (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> элементы управления представляют собой набор из двух или более взаимоисключающих вариантов для пользователя. Переключатели и флажки могут показаться работают так же, является важным отличием: когда пользователь выбирает переключатель, другие переключатели в той же группе, не могут быть выбраны также. В отличие от этого можно выбрать любое число флажков. Определение в переключателе информирует пользователя, «Вот набор вариантов, из которых можно выбрать только один».  
  
## <a name="using-the-control"></a>С помощью элемента управления  
 При <xref:System.Windows.Forms.RadioButton> нажатии элемента управления, его <xref:System.Windows.Forms.RadioButton.Checked%2A> свойству `true` и <xref:System.Windows.Forms.Control.Click> вызывается обработчик события. <xref:System.Windows.Forms.RadioButton.CheckedChanged> Событие возникает при значение <xref:System.Windows.Forms.RadioButton.Checked%2A> изменения свойств. Если <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> свойству `true` (по умолчанию), если выбран переключатель все остальные группы автоматически очищается. Это свойство обычно является равным только `false` при использовании кода проверки для убедитесь, что этот переключатель представляет допустимый параметр. Текст, отображаемый в элементе управления устанавливается с <xref:System.Windows.Forms.Control.Text%2A> свойство, которое может содержать клавиши быстрого доступа. Клавиша доступа позволяет пользователю «щелкните «элемент управления, нажав клавишу ALT, с помощью ключа доступа. Дополнительные сведения см. в разделе [как: Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) и [как: значение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 <xref:System.Windows.Forms.RadioButton> Управления могут иметь внешний вид кнопки, которая отображается при выбранном Если <xref:System.Windows.Forms.RadioButton.Appearance%2A> свойству <xref:System.Windows.Forms.Appearance.Button>. Переключатели можно также отобразить образов с помощью <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A> свойства. Дополнительные сведения см. в разделе [как: задать изображение, отображаемое элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RadioButton>  
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Общие сведения об элементе управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Общие сведения об элементе управления CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Практическое руководство. Создание переключателя для выбора одной из нескольких установок на базе элементов управления RadioButton в Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [Элемент управления RadioButton](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
