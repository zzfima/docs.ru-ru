---
title: "Практическое руководство. Рисование пользовательских пунктирных линий | Microsoft Docs"
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
  - "линии, пользовательский"
  - "линии, штриховые"
  - "линии, рисование"
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Рисование пользовательских пунктирных линий
Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет различные стили штриховых линий, входящие в перечисление <xref:System.Drawing.Drawing2D.DashStyle>.  Если эти стандартные стили штриховых линий не подходят, можно создать пользовательский шаблон штриховой линии.  
  
## Пример  
 Чтобы нарисовать пользовательскую штриховую линию, поместите длины штрихов и промежутков между ними в некоторый массив и присвойте его свойству <xref:System.Drawing.Pen.DashPattern%2A> объекта <xref:System.Drawing.Pen>.  В приведенном ниже примере рисуется пользовательская пунктирная линия на основе массива `{5, 2, 15, 4}`.  Умножив элементы этого массива на толщину пера, равную 5, получаем массив `{25, 10, 75, 20}`.  Получившиеся штрихи поочередно имеют длину 25 или 75, длина промежутков между ними поочередно равна 10 или 20.  
  
 Нарисованная штриховая линия показана на следующем рисунке.  Обратите внимание, что последний штрих должен иметь длину, меньшую 25 единиц, чтобы конец линии располагался в точке \(405, 5\).  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens6.png "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## Компиляция кода  
 Создайте форму Windows Forms и перейдите к обработчику события <xref:System.Windows.Forms.Control.Paint> этой формы.  Вставьте приведенный выше код в обработчик события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)