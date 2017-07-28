---
title: "Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях | Microsoft Docs"
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
  - "растровые изображения [Windows Forms], использование матриц цветов для прозрачных"
  - "изображения [Windows Forms], использование матриц цветов для прозрачных"
  - "матрицы, альфа-компоненты"
  - "прозрачность, матрицы цветов"
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях
Классы <xref:System.Drawing.Bitmap> \(наследующий у класса <xref:System.Drawing.Image>\) и <xref:System.Drawing.Imaging.ImageAttributes> предоставляют функции для чтения и записи значений пикселей.  Для изменения альфа\-компонентов во всем изображении можно использовать класс <xref:System.Drawing.Imaging.ImageAttributes>, либо можно вызывать метод <xref:System.Drawing.Bitmap.SetPixel%2A> класса <xref:System.Drawing.Bitmap> для изменения значений отдельных пикселей.  
  
## Пример  
 Класс <xref:System.Drawing.Imaging.ImageAttributes> содержит множество свойств, которые можно использовать для модификаций изображений при их отрисовке.  В следующем примере объект <xref:System.Drawing.Imaging.ImageAttributes> используется для установки значений всех альфа\-компонентов равными 80 процентам от их первоначальных значений.  Для этого выполняется инициализация матрицы цветов и установка в этой матрице масштабирующего коэффициента для альфа\-компонента равным 0,8.  Адрес матрицы цветов передается методу <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> объекта <xref:System.Drawing.Imaging.ImageAttributes>, а объект <xref:System.Drawing.Imaging.ImageAttributes> передается методу <xref:System.Drawing.Graphics.DrawString%2A> объекта <xref:System.Drawing.Graphics>.  
  
 В процессе отрисовки значения альфа\-компонентов растрового изображения преобразуются и становятся равными 80% от их первоначальных значений.  Это приводит к смешиванию изображения и фона.  Как показано на следующем рисунке, растровое изображение выглядит прозрачным, и сквозь него можно видеть сплошную черную линию.  
  
 ![Альфа&#45;сглаживание с использованием матрицы](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 В местах, где изображение покрывает белые участки фона, оно смешивается с белым цветом.  Там, где изображение пересекает черную линию, оно смешивается с черным цветом.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Альфа\-смешение цвета для линий и заливок](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)