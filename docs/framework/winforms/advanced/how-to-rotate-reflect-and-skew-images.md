---
title: "Практическое руководство. Поворот, отражение и наклон изображений | Microsoft Docs"
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
  - "изображения [Windows Forms], отражение"
  - "изображения [Windows Forms], поворот"
  - "изображения [Windows Forms], наклон"
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Поворот, отражение и наклон изображений
Изображение можно поворачивать, отражать и наклонять, указывая точки назначения для верхнего левого, верхнего правого и нижнего левого углов исходного изображения.  Эти три точки назначения определяют аффинное преобразование, которое отображает исходное прямоугольное изображение в параллелограмм.  
  
## Пример  
 Например, предположим, что исходное изображение представляет собой прямоугольник с верхним левым углом в точке \(0, 0\), верхним правым углом в точке \(100, 0\) и нижним левым углом в точке \(0, 50\).  Допустим, эти три точки отображаются в точки назначения следующим образом.  
  
|Исходная точка|Точка назначения|  
|--------------------|----------------------|  
|Верхний левый угол \(0, 0\)|\(200, 20\)|  
|Верхний правый угол \(100, 0\)|\(110, 100\)|  
|Нижний левый угол \(0, 50\)|\(250, 30\)|  
  
 На следующем рисунке показаны как исходное изображение, так и отображение этого изображения в параллелограмм.  Исходное изображение было наклонено, отражено, повернуто и сдвинуто.  Ось x, расположенная вдоль верхнего края исходного изображения, отображается в линию, проходящую через точки \(200, 20\) и \(110, 100\).  Ось y, расположенная вдоль левого края исходного изображения, отображается в линию, проходящую через точки \(200, 20\) и \(250, 30\).  
  
 ![Полосы](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 На приведенном ниже рисунке показано такое же преобразование, примененное к фотографическому изображению.  
  
 ![Преобразованный Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 На следующем рисунке показано аналогичное преобразование, примененное к метафайлу.  
  
 ![Преобразованный метафайл](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 В следующем примере создаются изображения, показанные на первом рисунке.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Не забудьте заменить путь и имя файла `Stripes.bmp` именем файла изображения и путем к нему в вашей системе.  
  
## См. также  
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)