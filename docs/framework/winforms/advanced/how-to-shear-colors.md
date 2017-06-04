---
title: "Практическое руководство. Сдвиг цветов | Microsoft Docs"
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
  - "цвета, сдвиг"
  - "цвета, преобразование с использованием матриц цветов"
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Сдвиг цветов
Пропорциональное изменение увеличивает или уменьшает компонент цвета на величину, пропорциональную другому компоненту цвета.  Например, рассмотрим преобразование, при котором красный компонент увеличивается на половину значения синего компонента.  При таком преобразовании цвет \(0,2; 0,5; 1\) превратится в цвет \(0,7; 0,5; 1\).  Новое значение красного компонента равняется 0,2 \+ \(1\/2\)\(1\) \= 0,7.  
  
## Пример  
 В следующем примере создается объект <xref:System.Drawing.Image> на основе файла ColorBars4.bmp.  После этого к каждому пикселю изображения применяется пропорциональное цветовое преобразование, описанное выше.  
  
 На следующем рисунке показаны как исходное изображение \(слева\), так и преобразованное изображение \(справа\).  
  
 ![Сместить цвета](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 В следующей таблице приводятся цветовые векторы четырех полос до и после преобразования.  
  
|До преобразования|После преобразования|  
|-----------------------|--------------------------|  
|\(0, 0, 1, 1\)|\(0.5, 0, 1, 1\)|  
|\(0.5, 1, 0.5, 1\)|\(0.75, 1, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(1, 1, 0, 1\)|  
|\(0.4, 0.4, 0.4, 1\)|\(0.6, 0.4, 0.4, 1\)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Подставьте вместо `ColorBars.bmp` имя имеющегося на вашем компьютере файла изображения и путь к нему.  
  
## См. также  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)