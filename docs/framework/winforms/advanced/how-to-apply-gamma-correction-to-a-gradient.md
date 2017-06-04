---
title: "Практическое руководство. Применение гамма-коррекции к градиенту | Microsoft Docs"
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
  - "градиентные кисти, гамма-коррекция"
  - "градиенты, гамма-коррекция"
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Применение гамма-коррекции к градиенту
Для кисти линейного градиента можно включить гамма\-коррекцию, присвоив свойству <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> этой кисти значение `true`.  Чтобы отключить гамма\-коррекцию, необходимо присвоить свойству <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> значение `false`.  По умолчанию гамма\-коррекция отключена.  
  
## Пример  
 В следующем примере создается кисть линейного градиента, которая затем используется для заливки двух прямоугольников.  При заливке первого прямоугольника гамма\-коррекция отключена, а при заливке второго включена.  
  
 Два нарисованных прямоугольника представлены на следующем рисунке.  Верхний прямоугольник, для которого не использовалась гамма\-коррекция, в середине кажется темным.  На поверхности нижнего прямоугольника, для которого гамма\-коррекция была включена, интенсивность цветов распределена более равномерно.  
  
 ![Градиент](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>   
 [Заливка фигур с помощью градиентной кисти](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)