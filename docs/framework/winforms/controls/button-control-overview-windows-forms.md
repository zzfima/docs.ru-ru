---
title: Общие сведения об элементе управления Button (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 88255882d3255eff112b9048a906182b64d75084
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="button-control-overview-windows-forms"></a>Общие сведения об элементе управления Button (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.Button> позволяет пользователю щелкнуть его для выполнения действия. При щелчке кнопки мышью элемент управления выглядит так, как будто его нажимают и отпускают. Когда пользователь нажимает кнопку, <xref:System.Windows.Forms.Control.Click> вызывается обработчик события. Поместить код в <xref:System.Windows.Forms.Control.Click> обработчик событий, чтобы выполнять любые действия, которые можно выбрать.  
  
 Текст, отображаемый на кнопке, содержится в <xref:System.Windows.Forms.Control.Text%2A> свойство. Если текст превышает ширину кнопки, он переходит к следующей строке. Тем не менее он будет обрезан, если элемент управления не может вместить высота. Дополнительные сведения см. в разделе [как: значение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md). <xref:System.Windows.Forms.Control.Text%2A> Свойство может содержать ключ доступа, который позволяет пользователю «щелкните «элемент управления, нажав клавишу ALT, с помощью ключа доступа. Дополнительные сведения см. в разделе [как: Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md). Внешний вид текста определяется <xref:System.Windows.Forms.Control.Font%2A> свойство и <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> свойства.  
  
 <xref:System.Windows.Forms.Button> Управления также может отображать изображения, используя <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A> свойства. Дополнительные сведения см. в разделе [как: задать изображение, отображаемое элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Button>  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
