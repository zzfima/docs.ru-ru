---
title: "Практическое руководство. Рисование прямоугольников с помощью пера | Microsoft Docs"
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
  - "перья, рисование прямоугольников"
  - "прямоугольники, рисование"
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Рисование прямоугольников с помощью пера
Чтобы нарисовать прямоугольник, нужно создать два объекта: объект <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Pen>.  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawRectangle%2A>, а объект <xref:System.Drawing.Pen> предназначен для хранения таких параметров рисуемой линии, как ее ширина и цвет.  
  
## Пример  
 В следующем примере будет построен прямоугольник, верхний левый угол которого расположен в точке с координатами \(10, 10\).  Ширина прямоугольника равна 100, а высота – 50.  Второй аргумент, передаваемый конструктору <xref:System.Drawing.Pen.%23ctor%2A>, указывает, что ширина пера равна 5 пикселей.  
  
 При рисовании прямоугольника перо располагается по центру границы данного прямоугольника.  Поскольку толщина пера равна 5, стороны прямоугольника рисуются шириной в 5 пикселей: 1 пиксель рисуется по самой границе, 2 пикселя рисуются внутри прямоугольника, и 2 пикселя — снаружи.  Дополнительные сведения о возможностях выравнивания пера см. в разделе [Практическое руководство. Задание толщины и выравнивания пера](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).  
  
 Нарисованный прямоугольник показан на следующем рисунке.  Пунктирные линии показывают, где был бы нарисован прямоугольник, если бы толщина пера была равна 1 пикселю.  Увеличенный вид верхнего левого угла прямоугольника демонстрирует, что жирные черные линии центрированы по этим пунктирным линиям.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens1.png "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)