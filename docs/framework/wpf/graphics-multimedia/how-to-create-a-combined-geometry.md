---
title: "Практическое руководство. Создание объединенных геометрических объектов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2be0471f27d26b145cc29847a08bf3bc3b1d51ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a>Практическое руководство. Создание объединенных геометрических объектов
В этом примере показано, как объединить геометрических объектов. Чтобы объединить два геометрических объекта, используйте <xref:System.Windows.Media.CombinedGeometry> объекта. Задать его <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> свойства два геометрических объекта для объединения и установить <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> свойство, которое определяет, как геометрические объекты будут объединены вместе, чтобы `Union`, `Intersect`, `Exclude`, или `Xor`.  
  
 Чтобы создать составной геометрический объект из двух или более геометрических объектов, используйте <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения geometry из `Exclude`.  Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Исключить результаты объединенного режима](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
Исключить объединенных геометрических объектов  
  
 В следующую разметку <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения из `Intersect`.  Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Функция Intersect результаты объединенного режима](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Intersect объединенных геометрических объектов  
  
 В следующую разметку <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения из `Union`.  Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Результаты объединения в режиме Union ](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
Объединение комбинированной геометрии  
  
 В следующую разметку <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения из `Xor`.  Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Результаты объединения в режиме Xor ](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
Xor объединенных геометрических объектов
