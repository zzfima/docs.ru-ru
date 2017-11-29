---
title: "Практическое руководство. Создание нескольких подконтуров внутри PathGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9a233df95f69a68c5410c5836dacd5ab2c239a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Практическое руководство. Создание нескольких подконтуров внутри PathGeometry
В этом примере показано, как создать несколько подпути в <xref:System.Windows.Media.PathGeometry>. Чтобы создать несколько вложенных путей, необходимо создать <xref:System.Windows.Media.PathFigure> для каждого вложенного пути.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два подпути, каждый из них треугольника.  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 Приведенный ниже показано, как создать с помощью нескольких подпути <xref:System.Windows.Shapes.Path> и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис атрибута. Каждый `M` создает новый подконтур, чтобы в примере создается два подпути, что каждый Рисование треугольника.  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченную версию из <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
