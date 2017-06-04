---
title: "Практическое руководство. Перечисление содержимого изображения визуального элемента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "перечисление содержимого визуального элемента [WPF]"
  - "получение значения DrawingGroup визуального элемента [WPF]"
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Практическое руководство. Перечисление содержимого изображения визуального элемента
Объект <xref:System.Windows.Media.Drawing> предоставляет модель объекта для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
## Пример  
 В следующем примере метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется для извлечения значения <xref:System.Windows.Media.DrawingGroup> объекта <xref:System.Windows.Media.Visual> и его перечисления.  
  
> [!NOTE]
>  При перечислении содержимого визуального объекта извлекаются объекты <xref:System.Windows.Media.Drawing>, а не базовое представление данных визуализации в виде списка инструкций векторной графики.  Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## См. также  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)