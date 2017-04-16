---
title: "Практическое руководство. Проверка нажатия с использованием геометрического объекта в качестве параметра | Microsoft Docs"
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
  - "Geometry - объекты, проверка нажатия визуальных объектов"
  - "проверка нажатия, визуальных объектов с помощью объектов Geometry"
  - "визуальные объекты, проверка нажатия"
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Проверка нажатия с использованием геометрического объекта в качестве параметра
В этом примере демонстрируется выполнение [проверки нажатия](GTMT) визуального объекта с использованием объекта <xref:System.Windows.Media.Geometry> в качестве параметра проверки нажатия.  
  
## Пример  
 В следующем примере показано, как настроить проверку нажатия, используя параметры <xref:System.Windows.Media.GeometryHitTestParameters> для метода <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>.  Значение <xref:System.Windows.Point>, которое было передано методу `OnMouseDown`, используется для создания объекта <xref:System.Windows.Media.Geometry>, чтобы расширить диапазон проверки нажатия.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Свойство <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> атрибута <xref:System.Windows.Media.GeometryHitTestResult> предоставляет сведения о результатах проверки нажатия, в которой в качестве параметра используется объект <xref:System.Windows.Media.Geometry>.  На следующем рисунке показано отношение между геометрическим объектом проверки нажатия \(синий круг\) и отображенным содержимым конечного визуального объекта \(красный квадрат\).  
  
 ![Схема IntersectionDetail, используемая в проверке нажатия](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Пересечение между геометрическим объектом проверки нажатия и конечным визуальным объектом  
  
 В следующем примере показано, как реализовать обратный вызов проверки нажатия, если в качестве параметра проверки нажатия используется объект <xref:System.Windows.Media.Geometry>.  Тип параметра `result` приводится к типу <xref:System.Windows.Media.GeometryHitTestResult>, чтобы извлечь значение свойства <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>.  Это значение позволяет определить, полностью или частично параметр проверки нажатия <xref:System.Windows.Media.Geometry> находится в отображаемом содержимом целевого объекта проверки нажатия.  В этом случае код примера только добавляет результаты проверки нажатия в список визуальных объектов, которые полностью содержатся в пределах границы целевого объекта.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  Обратный вызов <xref:System.Windows.Media.HitTestResult> не должен осуществляться, если для деталей пересечения возвращается значение <xref:System.Windows.Media.IntersectionDetail>.  
  
## См. также  
 [Проверка попадания на визуальном уровне](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Геометрия проверки нажатия в визуальном объекте](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)