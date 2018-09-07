---
title: Практическое руководство. Создание эллиптической дуги
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 7ca7d06aa25f8dfae648d8c54c8b95cc277ffbf9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087441"
---
# <a name="how-to-create-an-elliptical-arc"></a>Практическое руководство. Создание эллиптической дуги
В этом примере показано, как для рисования эллиптической дуги. Создание эллиптической дуги, использовать <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, и <xref:System.Windows.Media.ArcSegment> классы.  
  
## <a name="example"></a>Пример  
 В следующих примерах Эллиптическая дуга рисуется от (10, 100) (200,100). Дуга имеет <xref:System.Windows.Media.ArcSegment.Size%2A> 100 на 50 аппаратно независимых пикселей, <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 градусов <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> параметр `true`и <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> из <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], можно использовать синтаксис атрибута для описания пути.  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченные версии <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. на странице [Синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)  
  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], также можно нарисовать дугу эллипса, явным образом с помощью тегов объектов. Ниже приведен эквивалентный предшествующей [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Данный пример является частью большого примера. Полный пример см. в разделе [примеры геометрических объектов](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>См. также  
 [Создание кривой Безье второго порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [Создание кривой Безье третьего порядка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
