---
title: "Практическое руководство. Рисование текста в визуальном элементе | Microsoft Docs"
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
  - "рисование, текста на визуальных элементах"
  - "текст, рисование на визуальных элементах"
  - "оформление, рисование текста на визуальных элементах"
  - "визуальные элементы, рисование текста на"
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Рисование текста в визуальном элементе
В следующем примере показано, как нарисовать текст в <xref:System.Windows.Media.DrawingVisual> с помощью объекта <xref:System.Windows.Media.DrawingContext>.  Нарисованное содержимое возвращается путем вызова метода <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> объекта <xref:System.Windows.Media.DrawingVisual>.  Можно нарисовать рисунки и текст в контексте рисования.  
  
 Чтобы нарисовать текст в контексте рисования, используйте метод <xref:System.Windows.Media.DrawingContext.DrawText%2A> объекта <xref:System.Windows.Media.DrawingContext>.  Закончив рисование содержимого в контексте рисования, вызовите метод <xref:System.Windows.Media.DrawingContext.Close%2A>, чтобы закрыть контекст рисования и сохранить содержимое.  
  
## Пример  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Полный пример кода, из которого был взят предыдущий пример, см. на веб\-странице [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).