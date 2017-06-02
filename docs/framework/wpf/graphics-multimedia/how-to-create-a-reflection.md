---
title: "Практическое руководство. Создание отражения | Microsoft Docs"
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
  - "кисти, создание отражений"
  - "создание отражений"
  - "отражения, создание"
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Создание отражения
В этом примере показано использование <xref:System.Windows.Media.VisualBrush> для создания отражения.  Поскольку <xref:System.Windows.Media.VisualBrush> может отображать существующие визуальные элементы, эту возможность можно использовать для создания интересных визуальных эффектов, например отражения и увеличения.  
  
## Пример  
 В следующем примере <xref:System.Windows.Media.VisualBrush> используется для создания отражения <xref:System.Windows.Controls.Border>, содержащего несколько элементов.  На следующем рисунке показан результат данного примера.  
  
 ![Отраженный объект Visual](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.png "graphicsmm\_visualbrush\_reflection\_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Полный код с дополнительными примерами к практическому руководству по увеличению частей экрана и созданию отражений см. на веб\-странице [Пример "VisualBrush"](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
## См. также  
 <xref:System.Windows.Media.VisualBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)