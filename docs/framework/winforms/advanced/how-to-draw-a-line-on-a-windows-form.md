---
title: "Практическое руководство. Рисование линии в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Graphics.DrawLine"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "рисование линий"
  - "рисование, линии"
  - "примеры [Windows Forms], рисование линий в формах"
  - "линии, рисование"
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Рисование линии в Windows Forms
В этом примере на форме рисуется линия.  Обычно при рисовании на форме обрабатывается событие <xref:System.Windows.Forms.Control.Paint> формы и выполняется рисование с помощью свойства <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> класса <xref:System.Windows.Forms.PaintEventArgs>, как показано в следующем примере.  
  
## Пример  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## Отказоустойчивость  
 Для любого объекта, потребляющего системные ресурсы \(например для объектов <xref:System.Drawing.Pen>\), всегда нужно вызывать метод <xref:System.IDisposable.Dispose%2A>.  
  
## См. также  
 <xref:System.Drawing.Graphics.DrawLine%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)