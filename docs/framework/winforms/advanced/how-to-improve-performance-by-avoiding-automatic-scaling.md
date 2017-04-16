---
title: "Практическое руководство. Повышение производительности за счет отключения автоматического масштабирования | Microsoft Docs"
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
  - "автоматическое масштабирование"
  - "изображения [Windows Forms], повышение производительности"
  - "изображения [Windows Forms], использование без автоматического масштабирования"
  - "производительность, улучшение изображения"
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Повышение производительности за счет отключения автоматического масштабирования
Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] поддерживает автоматическое масштабирование выводимого на экран изображения, но этот процесс снижает производительность.  Для управления масштабом изображения можно также передавать методу <xref:System.Drawing.Graphics.DrawImage%2A> значения ширины и высоты прямоугольника назначения.  
  
 Например, в показанном ниже вызове метода <xref:System.Drawing.Graphics.DrawImage%2A> указывается верхний левый угол с координатами \(50, 30\), а прямоугольник назначения не определяется.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Хотя это простейший вариант метода <xref:System.Drawing.Graphics.DrawImage%2A>, если судить по количеству требуемых параметров, однако он необязательно является самым эффективным.  Если разрешение \(обычно 96 точек на дюйм\), используемое интерфейсом [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], отличается от разрешения, указанного в объекте <xref:System.Drawing.Image>, то метод <xref:System.Drawing.Graphics.DrawImage%2A> осуществляет масштабирование изображения.  Например, предположим, что объект <xref:System.Drawing.Image> имеет в ширину 216 пикселей, а хранящееся в этом объекте разрешение по горизонтали составляет 72 точки на дюйм.  Поскольку 216\/72 равно 3, метод <xref:System.Drawing.Graphics.DrawImage%2A> осуществляет масштабирование изображения таким образом, чтобы конечное изображение имело в ширину 3 дюйма при разрешении 96 точек на дюйм.  Таким образом, метод <xref:System.Drawing.Graphics.DrawImage%2A> выводит изображение шириной 96 x 3 \= 288 пикселей.  
  
 Даже если экранное разрешение отличается от 96 точек на дюйм, вполне вероятно, что интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] все равно осуществит масштабирование изображения, как если бы разрешение составляло 96 точек на дюйм.  Это происходит потому, что объект <xref:System.Drawing.Graphics> интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] связан с программной средой устройства и, когда [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] запрашивает экранное разрешение у программной среды устройства, результатом обычно является 96, независимо от фактического экранного разрешения.  Чтобы предотвратить автоматическое масштабирование, можно указать в параметрах метода <xref:System.Drawing.Graphics.DrawImage%2A> прямоугольник назначения.  
  
## Пример  
 В следующем примере одно и то же изображение рисуется два раза.  В первом случае ширина и высота прямоугольника назначения не указываются и осуществляется автоматическое масштабирование изображения.  Во втором случае ширина и высота прямоугольника назначения задаются явным образом \(в пикселях\) равными соответственно ширине и высоте исходного изображения.  На приведенном ниже рисунке показано дважды выведенное на экран изображение.  
  
 ![Масштабированная текстура](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Не забудьте заменить путь и имя файла Replace Texture.jpg именем файла изображения в вашей системе.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)