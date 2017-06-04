---
title: "Практическое руководство. Проверка попадания курсора Geometry визуальном объекте | Microsoft Docs"
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
  - "Geometry - объекты, визуальные объекты, составляющие"
  - "проверка нажатия, визуальных объектов, составляющих объекты Geometry"
  - "визуальные объекты, проверка нажатия"
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Проверка попадания курсора Geometry визуальном объекте
В данном примере показано, как выполнять [проверку попадания курсора](GTMT) на визуальный объект, состоящий из одного или нескольких объектов <xref:System.Windows.Media.Geometry>.  
  
## Пример  
 В следующем примере показано, как извлечь объект <xref:System.Windows.Media.DrawingGroup> из визуального объекта, который использует метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>.  Затем выполняется проверка попадания курсора на отображенное содержимое каждого рисунка объекта <xref:System.Windows.Media.DrawingGroup>, чтобы определить, на какой геометрический объект попал курсор.  
  
> [!NOTE]
>  Для определения попадания курсора на какую\-либо часть отображенного содержимого визуального объекта, в большинстве случаев следует использовать метод <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Метод <xref:System.Windows.Media.Geometry.FillContains%2A> — это перегруженный метод, который позволяет проводить проверку попадания курсора, с помощью объектов <xref:System.Windows.Point> или <xref:System.Windows.Media.Geometry>.  Если есть пересечение с геометрической фигурой, то оно может лежать за пределами границ заполнения.  В этом случае, возможно, потребуется вызов <xref:System.Windows.Media.Geometry.StrokeContains%2A> в дополнение к <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 Можно также предоставить <xref:System.Windows.Media.ToleranceType>, который используется в целях спрямления кривой Безье.  
  
> [!NOTE]
>  В данном примере не принимаются в расчет никакие преобразования или отсечения, которые могут быть применены к геометрической фигуре.  Кроме того, данный пример не будет работать с элементом управления со стилями, поскольку он не имеет никаких рисунков, непосредственно связанных с ним.  
  
## См. также  
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Проверка нажатия с использованием геометрии в качестве параметра](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)