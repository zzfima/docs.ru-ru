---
title: "Практическое руководство. Рисование линий с помощью пера | Microsoft Docs"
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
  - "линии, рисование"
  - "перья, рисование линий"
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Рисование линий с помощью пера
Чтобы нарисовать линию, нужно создать два объекта: объект <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Pen>.  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawLine%2A>, а объект <xref:System.Drawing.Pen> предназначен для хранения таких параметров рисуемой линии, как ее ширина и цвет.  
  
## Пример  
 В приведенном ниже примере демонстрируется рисование отрезка из точки с координатами \(20, 10\) в точку с координатами \(300, 100\).  В первой инструкции вызывается конструктор класса <xref:System.Drawing.Pen.%23ctor%2A> и создается черное перо.  Единственный аргумент, передаваемый конструктору <xref:System.Drawing.Pen.%23ctor%2A>, является объектом <xref:System.Drawing.Color>, созданным с помощью метода <xref:System.Drawing.Color.FromArgb%2A>.  Значения, используемые при создании объекта <xref:System.Drawing.Color> \(255, 0, 0, 0\), соответствуют альфа\-, красному, зеленому, синему компонентам цвета.  Приведенные значения определяют непрозрачное черное перо.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 <xref:System.Drawing.Pen>   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Перья, линии и прямоугольники в GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)