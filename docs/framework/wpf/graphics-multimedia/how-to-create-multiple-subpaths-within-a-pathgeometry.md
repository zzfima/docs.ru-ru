---
title: Практическое руководство. Создание нескольких подконтуров внутри PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353377"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>Практическое руководство. Создание нескольких подконтуров внутри PathGeometry
В этом примере показано, как создание нескольких подконтуров в <xref:System.Windows.Media.PathGeometry>. Чтобы создать несколько подконтуров, необходимо создать <xref:System.Windows.Media.PathFigure> для каждого вложенного пути.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два подконтуров, каждый из них треугольника.  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 В следующем примере показано, как создание нескольких подконтуров с помощью <xref:System.Windows.Shapes.Path> и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис атрибута. Каждый `M` создает новый вложенный путь, чтобы в примере создается два подконтуров, что каждый Рисование треугольника.  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченные версии <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. на странице [Синтаксис разметки пути](path-markup-syntax.md).)  
  
## <a name="see-also"></a>См. также
- [Общие сведения о классе Geometry](geometry-overview.md)
