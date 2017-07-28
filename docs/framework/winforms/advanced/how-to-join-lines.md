---
title: "Практическое руководство. Соединение линий | Microsoft Docs"
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
  - "стиль соединения линий с фасками"
  - "рисование, соединение линий"
  - "графика, соединение линий"
  - "GraphicsPath - объект"
  - "соединение линий"
  - "линии, соединение"
  - "стиль соединения линий с фацетами"
  - "Pen - класс"
  - "стиль соединения линий с закруглением"
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Соединение линий
Соединение линий — это общая область, образуемая двумя линиями с соприкасающимися или пересекающимися концами.  Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет три стиля соединения линий: фацетное соединение, скошенное соединение и скругленное соединение.  Стиль соединения линий является свойством класса <xref:System.Drawing.Pen>.  После задания стиля соединения линий для объекта <xref:System.Drawing.Pen> этот стиль будет применяться ко всем соединенным линиям любого объекта <xref:System.Drawing.Drawing2D.GraphicsPath>, для рисования которого используется данное перо.  
  
 Результат скошенного соединения линий показан на следующем рисунке.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens5.png "pens5")  
  
## Пример  
 Для указания стиля соединения линий служит свойство <xref:System.Drawing.Pen.LineJoin%2A> класса <xref:System.Drawing.Pen>.  В примере демонстрируется использование скошенного соединения горизонтальной и вертикальной линий.  В следующем фрагменте кода значение <xref:System.Drawing.Drawing2D.LineJoin>, присвоенное свойству <xref:System.Drawing.Pen.LineJoin%2A> является членом перечисления <xref:System.Drawing.Drawing2D.LineJoin>.  Другие члены перечисления <xref:System.Drawing.Drawing2D.LineJoin> — <xref:System.Drawing.Drawing2D.LineJoin> и <xref:System.Drawing.Drawing2D.LineJoin>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)