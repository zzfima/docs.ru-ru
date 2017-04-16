---
title: "Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур | Microsoft Docs"
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
  - "фигуры, создание из линий"
  - "фигуры, создание из фигур"
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур
Чтобы создать изображение, создайте объект <xref:System.Drawing.Drawing2D.GraphicsPath>, а затем вызовите его методы, например <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> или <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, для добавления к изображению примитивов.  
  
## Пример  
 В следующем примере кода создается контур, состоящий из двух фигур.  
  
-   В первом примере создается контур, состоящий из одной фигуры.  Фигура представляет собой одну дугу.  Дуга имеет угол развертки, равный 180 градусам, в принятой по умолчанию системе координат он соответствует движению против часовой стрелки.  
  
-   Во втором примере создается контур, состоящий из двух фигур.  Первая фигура представляет собой дугу, за которой следует линия.  Вторая фигура является прямой, за которой следуют кривая и другая прямая.  Первая фигура незамкнутая, а вторая — замкнутая.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)