---
title: "Общие сведения об элементе управления Button (Windows Forms) | Microsoft Docs"
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
  - "Button"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Button - элемент управления [Windows Forms], сведения об элементе управления Button"
  - "кнопки, сведения о кнопках"
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения об элементе управления Button (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.Button> \(кнопка\) служит для выполнения действия с помощью мыши.  Если нажать кнопку, она выглядит так, словно она нажата и отпущена.  При нажатии на кнопку вызывается обработчик событий <xref:System.Windows.Forms.Control.Click>.  В обработчик событий <xref:System.Windows.Forms.Control.Click> помещается код, отвечающий за выполнение нужного действия.  
  
 Текст, отображающийся на кнопке, содержится в свойстве <xref:System.Windows.Forms.Control.Text%2A>.  Если текст превышает ширину кнопки, он переходит на следующую строку.  Однако если высота элемента управления не может изменяться, текст обрезается.  Дополнительные сведения см. в разделе [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  Свойство <xref:System.Windows.Forms.Control.Text%2A> может содержать клавишу доступа, что позволяет пользователю выполнять действие, аналогичное щелчку элемента управления, нажав клавишу ALT одновременно с клавишей доступа.  Дополнительные сведения см. в разделе [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  Внешний вид текста управляется свойством <xref:System.Windows.Forms.Control.Font%2A> и свойством <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>.  
  
 В элементе управления <xref:System.Windows.Forms.Button> можно также отображать рисунки с помощью свойств <xref:System.Windows.Forms.ButtonBase.Image%2A> и <xref:System.Windows.Forms.ButtonBase.ImageList%2A>.  Дополнительные сведения см. в разделе [Практическое руководство. Определение изображения, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.Button>   
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)   
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)