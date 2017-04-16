---
title: "Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения | Microsoft Docs"
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
  - "растровые изображения [Windows Forms], использование текстур"
  - "изображения [Windows Forms], использование с кистями"
  - "фигуры, заполнение изображениями"
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения
Замкнутую фигуру можно залить текстурой, используя для этого классы <xref:System.Drawing.Image> и <xref:System.Drawing.TextureBrush>.  
  
## Пример  
 В следующем примере осуществляется заливка эллипса текстурой с изображением.  В коде создается объект <xref:System.Drawing.Image>, а затем адрес этого объекта <xref:System.Drawing.Image> передается в качестве параметра конструктору <xref:System.Drawing.TextureBrush.%23ctor%2A>.  Третья инструкция осуществляет масштабирование изображения, а четвертая инструкция выполняет заливку эллипса повторяющимися экземплярами этого масштабированного изображения.  
  
 В приведенном ниже коде свойство <xref:System.Drawing.TextureBrush.Transform%2A> содержит преобразование, которое применяется к изображению перед его прорисовкой.  Предположим, что исходное изображение имеет ширину 640 пикселей и высоту 480 пикселей.  Преобразование уменьшает изображение до размера 75×75, устанавливая горизонтальный и вертикальный коэффициенты масштабирования.  
  
> [!NOTE]
>  В приведенном ниже примере размер изображения равен 75×75, в то время как эллипс имеет размер 150×250.  Поскольку изображение меньше, чем заполняемый им эллипс, используется мозаичное заполнение эллипса изображением.  Мозаичное заполнение означает, что изображение многократно повторяется в горизонтальном и вертикальном направлениях, пока не достигает границы фигуры.  Дополнительные сведения о мозаичном заполнении см. в разделе [Практическое руководство. Мозаичное заполнение фигуры заданным изображением](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)