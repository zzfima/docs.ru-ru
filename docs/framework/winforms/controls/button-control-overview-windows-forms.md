---
title: Общие сведения об элементе управления Button
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747077"
---
# <a name="button-control-overview-windows-forms"></a>Общие сведения об элементе управления Button (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.Button> позволяет пользователю щелкнуть его для выполнения действия. При щелчке кнопки мышью элемент управления выглядит так, как будто его нажимают и отпускают. Каждый раз, когда пользователь нажимает кнопку, вызывается обработчик событий <xref:System.Windows.Forms.Control.Click>. Код размещается в обработчике событий <xref:System.Windows.Forms.Control.Click> для выполнения любых действий, которые вы выбираете.  
  
 Текст, отображаемый на кнопке, содержится в свойстве <xref:System.Windows.Forms.Control.Text%2A>. Если текст превышает ширину кнопки, он будет перенесен на следующую строку. Однако он будет обрезан, если элемент управления не может соответствовать общей высоте. Дополнительные сведения см. в разделе [как задать текст, отображаемый элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md). Свойство <xref:System.Windows.Forms.Control.Text%2A> может содержать ключ доступа, позволяющий пользователю "щелкнуть" элемент управления, нажав клавишу ALT с клавишей доступа. Дополнительные сведения см. [в разделе инструкции. Создание ключей доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md). Внешний вид текста определяется свойством <xref:System.Windows.Forms.Control.Font%2A> и свойством <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>.  
  
 <xref:System.Windows.Forms.Button> элемент управления может также отображать изображения с помощью свойств <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A>. Дополнительные сведения см. в разделе [как задать изображение, отображаемое элементом управления Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Button>
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Элемент управления Button](button-control-windows-forms.md)
