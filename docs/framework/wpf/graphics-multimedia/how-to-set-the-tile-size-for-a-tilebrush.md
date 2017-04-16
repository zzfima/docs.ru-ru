---
title: "Как установить размер мозаики для TileBrush | Microsoft Docs"
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
  - "TileBrush, Размер элементов мозаики"
  - "Viewport - свойство TileBrush"
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Как установить размер мозаики для TileBrush
В этом примере демонстрируется, как установить размер мозаики для <xref:System.Windows.Media.TileBrush>.  По умолчанию <xref:System.Windows.Media.TileBrush> создает один фрагмент мозаики, который полностью заполняет область раскрашивания.  Это поведение можно переопределить, задав свойства <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>.  
  
 Свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> определяет размер фрагмента мозаики для <xref:System.Windows.Media.TileBrush>.  По умолчанию значение свойства <xref:System.Windows.Media.TileBrush.Viewport%2A> связано с размером области раскрашивания.  Чтобы свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> определяло абсолютный размер мозаики, присвойте свойству <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> значение <xref:System.Windows.Media.BrushMappingMode>.  
  
## Пример  
 Следующий пример использует <xref:System.Windows.Media.ImageBrush>, тип объекта <xref:System.Windows.Media.TileBrush>, для заполнения прямоугольника мозаикой.  В примере каждый фрагмент мозаики устанавливается в отношении 50% к 50% области вывода \(прямоугольник\).  В результате, прямоугольник раскрашивается с четырьмя проекциями изображения.  
  
 На следующем рисунке показан результат данного примера.  
  
 ![Пример мозаики с использованием кисти изображения](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 Следующий пример создает объект <xref:System.Windows.Media.ImageBrush>, задает для его свойства <xref:System.Windows.Media.TileBrush.Viewport%2A> значение `0,0,25,25` и для свойства <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> — значение <xref:System.Windows.Media.BrushMappingMode>, и использует их для раскрашивания другого прямоугольника.  В результате, кисть создает мозаику с шириной 25 [пикселей](GTMT) и высотой 25 [пикселей](GTMT).  
  
 На следующем рисунке показан результат данного примера.  
  
 ![Мозаичная кисть TileBrush с областью отображения 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Следующий пример является частью большого примера.  Полный код примера см. в разделе [Пример ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Хотя этот пример использует класс <xref:System.Windows.Media.ImageBrush>, свойства <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> ведут себя одинаково для других объектов <xref:System.Windows.Media.TileBrush>, то есть для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>.  Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> и других объектах <xref:System.Windows.Media.TileBrush>, см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## См. также  
 <xref:System.Windows.Media.TileBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Создание различных шаблонов мозаики с помощью TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)