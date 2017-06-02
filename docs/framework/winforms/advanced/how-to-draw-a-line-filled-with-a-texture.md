---
title: "Практическое руководство. Рисование линии с текстурным заполнением | Microsoft Docs"
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
  - "рисование линий, текстура"
  - "рисование, линии"
  - "линии, текстура"
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Рисование линии с текстурным заполнением
Вместо рисования линии сплошным цветом можно нарисовать линию с текстурной заливкой.  Для рисования прямых и кривых линий с текстурной заливкой необходимо создать объект <xref:System.Drawing.TextureBrush> и передать этот объект <xref:System.Drawing.TextureBrush> конструктору <xref:System.Drawing.Pen.%23ctor%2A>.  Растровое изображение, связанное с текстурной кистью, заполняет плоскость рисования, оставаясь невидимым, и, когда перо рисует линию или кривую, соответствующие пиксели текстуры, расположенные под пером, становятся видимыми.  
  
## Пример  
 В следующем примере показано создание объекта <xref:System.Drawing.Bitmap> из файла `Texture1.jpg`.  Это растровое изображение используется для создания объекта <xref:System.Drawing.TextureBrush>, а объект <xref:System.Drawing.TextureBrush> используется, в свою очередь, для создания объекта <xref:System.Drawing.Pen>.  Вызов метода <xref:System.Drawing.Graphics.DrawImage%2A> формирует растровое изображение с верхним левым углом в точке \(0, 0\).  Вызов <xref:System.Drawing.Graphics.DrawEllipse%2A> использует объект <xref:System.Drawing.Pen>, чтобы нарисовать текстурированный эллипс.  
  
 На следующем рисунке показаны растровое изображение и текстурированный эллипс.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## Компиляция кода  
 Создайте форму Windows Forms и перейдите к обработчику события <xref:System.Windows.Forms.Control.Paint> этой формы.  Вставьте приведенный выше код в обработчик события <xref:System.Windows.Forms.Control.Paint>.  Подставьте вместо  `Texture.jpg` имя имеющегося на вашем компьютере файла изображения.  
  
## См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)