---
title: "Практическое руководство. Рисование текста на фоне элемента управления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "фоны, рисование текста на"
  - "элементы управления, рисование текста на фоне"
  - "рисование, текста на фоне элементов управления"
  - "текст, рисование на фоне элементов управления"
  - "оформление, рисование текста на фоне элементов управления"
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Рисование текста на фоне элемента управления
Можно нарисовать текст непосредственно на фоне элемента управления с помощью преобразования текстовой строки в объект <xref:System.Windows.Media.FormattedText> и затем отобразив его в объекте <xref:System.Windows.Media.DrawingContext> элемента управления.  Можно также использовать этот метод для рисования на фоне объектов, производных от объекта <xref:System.Windows.Controls.Panel>, например <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.  
  
 ![Элементы управления, отображающие текст в качестве фона](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Пример элементов управления с пользовательским текстом на фоне  
  
## Пример  
 Чтобы рисовать на фоне элемента управления, создайте новый объект <xref:System.Windows.Media.DrawingBrush> и нарисуйте преобразованный текст в классе <xref:System.Windows.Media.DrawingContext> объекта.  Затем назначьте новый объект <xref:System.Windows.Media.DrawingBrush> свойству фона элемента управления.  
  
 В следующем примере показано, как создать объект <xref:System.Windows.Media.FormattedText> и рисовать на фоне объектов <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## См. также  
 <xref:System.Windows.Media.FormattedText>   
 [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)