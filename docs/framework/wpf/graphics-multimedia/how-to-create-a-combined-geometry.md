---
title: "Практическое руководство. Создание объединенных геометрических объектов | Microsoft Docs"
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
  - "комбинирование геометрических объектов"
  - "геометрические объекты, объединение"
  - "графика, комбинирование геометрических объектов"
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание объединенных геометрических объектов
В этом примере демонстрируется способ объединения геометрических объектов.  Чтобы объединить два геометрических объекта, используйте объект <xref:System.Windows.Media.CombinedGeometry>.  Необходимо задать в его свойствах <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> два геометрических объекта для объединения и установить свойство <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>, которое определяет способ объединения геометрических объектов, в значение `Union`, `Intersect`, `Exclude` или `Xor`.  
  
 Чтобы создать составной геометрический объект из двух или более геометрических объектов, используется <xref:System.Windows.Media.GeometryGroup>.  
  
## Пример  
 В следующем примере <xref:System.Windows.Media.CombinedGeometry> задается режимом объединения геометрических объектов `Exclude`.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> задаются как круги с одинаковыми радиусами, но с центрами, смещенными на 50.  
  
 [!code-xml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Результаты объединенного режима Exclude](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.png "mil\_task\_combined\_geometry\_exclude")  
Объединение геометрических объектов в режиме Exclude  
  
 В следующем примере разметки <xref:System.Windows.Media.CombinedGeometry> задается режимом объединения `Intersect`.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> задаются как круги с одинаковыми радиусами, но с центрами, смещенными на 50.  
  
 [!code-xml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Результаты объединенного режима Intersect](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.png "mil\_task\_combined\_geometry\_intersect")  
Объединение геометрических объектов в режиме Intersect  
  
 В следующем примере разметки <xref:System.Windows.Media.CombinedGeometry> задается режимом объединения `Union`.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> задаются как круги с одинаковыми радиусами, но с центрами, смещенными на 50.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Результаты объединенного режима Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
Объединение геометрических объектов в режиме Union  
  
 В следующем примере разметки <xref:System.Windows.Media.CombinedGeometry> задается режимом объединения `Xor`.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> задаются как круги с одинаковыми радиусами, но с центрами, смещенными на 50.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Результаты объединенного режима Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
Объединение геометрических объектов в режиме Xor