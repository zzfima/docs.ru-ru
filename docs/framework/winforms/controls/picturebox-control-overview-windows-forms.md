---
title: "Общие сведения об элементе управления PictureBox (Windows Forms) | Microsoft Docs"
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
  - "PictureBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления изображением, сведения об элементах управления изображения"
  - "элементы управления Picture, сведения об элементах управления Picture"
  - "PictureBox - элемент управления [Windows Forms], сведения об элементах управления PictureBox"
ms.assetid: e5befee7-dc29-4888-a7c4-3b177e394112
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Общие сведения об элементе управления PictureBox (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.PictureBox> предназначен для отображения графических объектов в различных форматах. Это может быть растровое изображение \(файл BMP\), пиктограмма \(файл ICO\), метафайл \(файл WMF или EMF\), а также файлы GIF и JPEG.  
  
## Ключевые свойства и методы  
 Отображаемое изображение определяется свойством <xref:System.Windows.Forms.PictureBox.Image%2A>, которое может быть задано во время выполнения или в режиме разработки.  Кроме того, изображение можно задать путем указания значения свойства <xref:System.Windows.Forms.PictureBox.ImageLocation%2A> с последующей загрузкой изображения в синхронном режиме с помощью метода <xref:System.Windows.Forms.PictureBox.Load%2A> или в асинхронном режиме с помощью метода <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>.  Свойство <xref:System.Windows.Forms.PictureBox.SizeMode%2A> управляет соответствием размеров рисунка и элемента управления.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение размера или размещения изображения во время выполнения](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md).  
  
## См. также  
 <xref:System.Windows.Forms.PictureBox>   
 [Практическое руководство. Загрузка изображения с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Практическое руководство. Изменение размера или размещения изображения во время выполнения](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)