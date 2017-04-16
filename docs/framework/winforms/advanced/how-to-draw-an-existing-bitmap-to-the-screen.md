---
title: "Практическое руководство. Рисование существующего точечного рисунка на экране | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "растровые изображения [Windows Forms], отображение в формах Windows Forms"
  - "растровые изображения [Windows Forms], загрузка в приложения Windows Forms"
  - "изображения [Windows Forms], отображение в формах Windows Forms"
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Рисование существующего точечного рисунка на экране
Существующее изображение очень просто нарисовать на экране.  Сначала необходимо создать объект <xref:System.Drawing.Bitmap> с помощью конструктора растрового изображения, который принимает имя файла, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.  Этот конструктор поддерживает изображения нескольких форматов, включая BMP, GIF, JPEG, PNG, TIFF.  После создания объекта <xref:System.Drawing.Bitmap>, передайте такой объект <xref:System.Drawing.Bitmap> в метод <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics>.  
  
## Пример  
 В этом примере создается объект <xref:System.Drawing.Bitmap> на основе файла в формате JPEG и на экране рисуется соответствующее растровое изображение с верхним левым углом в точке \(60, 10\).  
  
 На следующем рисунке показано растровое изображение, выведенное на экран в указанном месте.  
  
 ![Положение изображения](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)