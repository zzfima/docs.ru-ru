---
title: Практическое руководство. Создание нескольких подконтуров внутри PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 5b129b1bacb5dc2cba87376e8df70e115a5ebd72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559336"
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
