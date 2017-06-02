---
title: "Практическое руководство. Преобразование цветов изображения | Microsoft Docs"
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
  - "растровые изображения [Windows Forms], изменение цветов"
  - "цвета изображения [Windows Forms]"
  - "изображения [Windows Forms], изменение цветов"
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Преобразование цветов изображения
Преобразование добавляет некоторое значение к одному или нескольким из четырех компонентов цвета.  Элементы матрицы цветов, соответствующие преобразованиями, приводятся в следующей таблице.  
  
|Преобразуемый компонент|Элемент матрицы|  
|-----------------------------|---------------------|  
|Красный|\[4\]\[0\]|  
|Зеленый|\[4\]\[1\]|  
|Синий|\[4\]\[2\]|  
|Альфа|\[4\]\[3\]|  
  
## Пример  
 В следующем примере объект <xref:System.Drawing.Image> создается на основе файла ColorBars.bmp.  После этого к красному компоненту каждого из пикселей изображения добавляется значение 0,75.  Исходное изображение отображается вместе с преобразованным изображением.  
  
 На следующем рисунке показаны как исходное изображение \(слева\), так и преобразованное изображение \(справа\).  
  
 ![Преобразовать цвета](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 В следующей таблице приводятся цветовые векторы четырех полос до и после преобразования.  Обратите внимание, что поскольку наибольшее значение компонента цвета равно 1, красный компонент во второй строке не меняется.  \(Аналогично наименьшим значением компонента цвета является 0.\)  
  
|До преобразования|После преобразования|  
|-----------------------|--------------------------|  
|Черный \(0, 0, 0, 1\)|\(0.75, 0, 0, 1\)|  
|Красный \(1, 0, 0, 1\)|\(1, 0, 0, 1\)|  
|Зеленый \(0, 1, 0, 1\)|\(0.75, 1, 0, 1\)|  
|Синий \(0, 0, 1, 1\)|\(0.75, 0, 1, 1\)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Замените путь и имя файла `ColorBars.bmp`  именем файла изображения в вашей системе.  
  
## См. также  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)