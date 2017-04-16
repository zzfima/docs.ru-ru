---
title: "Практическое руководство. Задание толщины и выравнивания пера | Microsoft Docs"
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
  - "перья, установка выравнивания"
  - "перья, установка ширины"
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Задание толщины и выравнивания пера
При создании объекта <xref:System.Drawing.Pen> можно указать толщину пера в качестве одного из параметров конструктора.  Можно также изменять толщину пера с помощью свойства <xref:System.Drawing.Pen.Width%2A> класса <xref:System.Drawing.Pen>.  
  
 Абстрактная линия имеет нулевую толщину.  При рисовании линии толщиной в один пиксель пиксели центрируются по абстрактной линии.  Если толщина рисуемой линии больше одного пикселя, то пиксели либо центрируются по абстрактной линии, либо располагаются по одну сторону от этой линии.  Для указания того, как следует располагать пиксели, рисуемые некоторым пером, относительно абстрактной линии, служит свойство выравнивания соответствующего объекта <xref:System.Drawing.Pen>.  
  
 Значения <xref:System.Drawing.Drawing2D.PenAlignment>, <xref:System.Drawing.Drawing2D.PenAlignment> и <xref:System.Drawing.Drawing2D.PenAlignment>, которые используются в приведенном ниже примере кода, являются членами перечисления <xref:System.Drawing.Drawing2D.PenAlignment>.  
  
 В следующем примере кода дважды выполняется рисование линии. В первый раз линия рисуется черным пером толщиной 1, а во второй — зеленым пером толщиной 10.  
  
### Изменение толщины пера  
  
-   Установите значение свойства <xref:System.Drawing.Pen.Alignment%2A> равным to <xref:System.Drawing.Drawing2D.PenAlignment> \(значение по умолчанию\), чтобы указать, что рисуемые зеленым пером пиксели должны быть центрированы по абстрактной линии.  Нарисованная линия показана на следующем рисунке.  
  
     ![Перья](../../../../docs/framework/winforms/advanced/media/pens1a.png "pens1A")  
  
     В следующем примере кода дважды выполняется рисование прямоугольника. В первый раз прямоугольник рисуется черным пером толщиной 1, а во второй — зеленым пером толщиной 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### Изменение выравнивания пера  
  
-   Установите значение свойства <xref:System.Drawing.Pen.Alignment%2A> равным <xref:System.Drawing.Drawing2D.PenAlignment>, чтобы указать, что рисуемые зеленым пером пиксели должны быть центрированы по границе прямоугольника.  
  
     Нарисованный прямоугольник показан на следующем рисунке.  
  
     ![Перья](../../../../docs/framework/winforms/advanced/media/pens2.png "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### Создание вложенного пера  
  
-   Измените выравнивание зеленого пера, модифицировав третью инструкцию приведенного выше примера следующим образом:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Теперь пиксели жирной зеленой линии располагаются внутри прямоугольника, как показано на следующем рисунке.  
  
     ![Перья](../../../../docs/framework/winforms/advanced/media/pens3.png "pens3")  
  
## См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)