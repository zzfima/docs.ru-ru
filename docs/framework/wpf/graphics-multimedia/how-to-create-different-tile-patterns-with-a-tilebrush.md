---
title: "Практическое руководство. Создание различных шаблонов с помощью TileBrush | Microsoft Docs"
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
  - "создание, шаблонов мозаики с помощью TileBrush"
  - "шаблоны мозаики, создание"
  - "TileBrush, создание шаблонов мозаики"
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Создание различных шаблонов с помощью TileBrush
В этом примере показывается использование свойства <xref:System.Windows.Media.TileBrush.TileMode%2A> <xref:System.Windows.Media.TileBrush> для создания шаблона.  
  
 Свойство <xref:System.Windows.Media.TileBrush.TileMode%2A> позволяет указать, как повторяется, т.е. выкладывается, содержимое <xref:System.Windows.Media.TileBrush> для заполнения выходной области.  Чтобы создать шаблон, установите <xref:System.Windows.Media.TileBrush.TileMode%2A> в <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode> или в <xref:System.Windows.Media.TileMode>.  Необходимо также задать <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush> так, чтобы она была меньше области, которая заполняется; в противном случае будет выведен только один фрагмент, независимо от того, какое задано значение <xref:System.Windows.Media.TileBrush.TileMode%2A>.  
  
## Пример  
 В следующем примере создаются пять объектов <xref:System.Windows.Media.DrawingBrush>, каждому из них присваиваются различные значения <xref:System.Windows.Media.TileBrush.TileMode%2A>, и затем они используются для рисования пяти прямоугольников.  Хотя этот пример использует класс <xref:System.Windows.Media.DrawingBrush> для демонстрации поведения <xref:System.Windows.Media.TileBrush.TileMode%2A>, свойство <xref:System.Windows.Media.TileBrush.TileMode%2A> работает одинаково для всех объектов <xref:System.Windows.Media.TileBrush>, т.е. для <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush> и <xref:System.Windows.Media.DrawingBrush>.  
  
 На следующем рисунке показан результат данного примера.  
  
 ![Пример мозаичного вывода TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm\_DrawingBrushTileModeExample")  
Шаблоны мозаики, созданные с помощью свойства TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## См. также  
 [Установка размера мозаики для TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)