---
title: "Общие сведения об элементе управления Label (Windows Forms) | Microsoft Docs"
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
  - "Label"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "изображения [Windows Forms], отображение в надписях"
  - "Label - элемент управления [Windows Forms], об элементе управления Label"
  - "подписи"
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения об элементе управления Label (Windows Forms)
Элементы управления Windows Forms <xref:System.Windows.Forms.Label> предназначены для отображения текста или изображений, которые пользователь не может изменить с клавиатуры.  Они используются для идентификации объектов в форме — например, для описания, что произойдет с элементом управления после выполнения на нем щелчка мышью, или для отображения сведений в ответ на процесс или событие времени выполнения в приложении.  Например, имеется возможность использовать надписи для добавления описательных заголовков в текстовые поля, списки, поля со списком и т.д.  Кроме того, возможно написание кода, который изменяет текст, отображаемый в надписи, в ответ на события во время выполнения.  Например, если приложению требуется несколько минут на обработку изменения, можно отобразить в надписи сообщение о статусе обработки.  
  
## Работа с элементом управления Label  
 Так как элемент управления <xref:System.Windows.Forms.Label> не может получать фокус, он может также использоваться для создания клавиш доступа для других элементов управления.  Клавиша доступа позволяет пользователю выбрать другой элемент управления, используя сочетание клавиши ALT и заданной клавиши.  Дополнительные сведения содержатся в разделе [Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) и [Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).  
  
 Отображаемый в надписи текст содержится в свойстве <xref:System.Windows.Forms.Label.Text%2A>.  Свойство <xref:System.Windows.Forms.Label.TextAlign%2A> позволяет задать выравнивание текста в надписи.  Дополнительные сведения см. в разделе [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.Label>   
 [Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)