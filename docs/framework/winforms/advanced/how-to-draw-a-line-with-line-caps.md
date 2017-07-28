---
title: "Практическое руководство. Рисование линий с наконечниками | Microsoft Docs"
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
  - "рисование линий, завершения отрезков"
  - "рисование, линии"
  - "линии, рисование"
  - "перья, рисование линий"
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Рисование линий с наконечниками
На одном или другом конце линии можно рисовать одну из нескольких специальных фигур, называемых наконечниками.  В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] поддерживается несколько типов наконечников, например круг, квадрат, ромб и стрелка.  
  
## Пример  
 Можно определять наконечники для начала линии \(начальный наконечник\), для конца линии \(конечный наконечник\) или для штрихов пунктирной линии \(штриховой наконечник\).  
  
 В следующем примере рисуется линия со стрелкой на одном конце и кружком на другом конце.  Нарисованная линия показана на следующем рисунке.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens4.png "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## Компиляция кода  
  
-   Создайте форму Windows Forms и перейдите к обработчику события <xref:System.Windows.Forms.Control.Paint> этой формы.  Вставьте приведенный пример кода в обработчик события <xref:System.Windows.Forms.Control.Paint> и передайте `e` в качестве объекта <xref:System.Windows.Forms.PaintEventArgs>.  
  
## См. также  
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=fullName>   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)