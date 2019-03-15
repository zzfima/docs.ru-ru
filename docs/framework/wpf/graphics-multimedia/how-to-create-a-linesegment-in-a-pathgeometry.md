---
title: Практическое руководство. Создание LineSegment в PathGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: a50c98ccc3f6d517e0917cb774af4d49d2bfa7a3
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57845636"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="90aca-102">Практическое руководство. Создание LineSegment в PathGeometry</span><span class="sxs-lookup"><span data-stu-id="90aca-102">How to: Create a LineSegment in a PathGeometry</span></span>

<span data-ttu-id="90aca-103">В этом примере показано, как создать сегмент линии.</span><span class="sxs-lookup"><span data-stu-id="90aca-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="90aca-104">Чтобы создать сегмент линии, используйте <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, и <xref:System.Windows.Media.LineSegment> классы.</span><span class="sxs-lookup"><span data-stu-id="90aca-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>

## <a name="example"></a><span data-ttu-id="90aca-105">Пример</span><span class="sxs-lookup"><span data-stu-id="90aca-105">Example</span></span>

<span data-ttu-id="90aca-106">В следующем примере рисуется <xref:System.Windows.Media.LineSegment> из (10, 50) к (200, 70).</span><span class="sxs-lookup"><span data-stu-id="90aca-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="90aca-107">На следующем рисунке показан итоговый <xref:System.Windows.Media.LineSegment>; для показа системы координат добавлена фоновая сетка.</span><span class="sxs-lookup"><span data-stu-id="90aca-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>

<span data-ttu-id="90aca-108">![LineSegment в PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") LineSegment, соединяющей (10,50) к (200,70)</span><span class="sxs-lookup"><span data-stu-id="90aca-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") A LineSegment drawn from (10,50) to (200,70)</span></span>

<span data-ttu-id="90aca-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="90aca-109">[xaml]</span></span>

<span data-ttu-id="90aca-110">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно использовать синтаксис атрибута для описания пути.</span><span class="sxs-lookup"><span data-stu-id="90aca-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

<span data-ttu-id="90aca-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="90aca-111">[xaml]</span></span>

<span data-ttu-id="90aca-112">(Обратите внимание, что этот синтаксис атрибута фактически создает <xref:System.Windows.Media.StreamGeometry>, облегченные версии <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="90aca-112">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="90aca-113">Дополнительные сведения см. на странице [Синтаксис разметки пути](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="90aca-113">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>

<span data-ttu-id="90aca-114">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] сегмент линии можно также начертить с использованием синтаксиса элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="90aca-114">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="90aca-115">Следующий пример эквивалентен предыдущему примеру [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90aca-115">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1">
  <Path.Data>
    <PathGeometry>
      <PathFigure StartPoint="10,50">
        <LineSegment Point="200,70" />
      </PathFigure>
    </PathGeometry>
  </Path.Data>
</Path>
```

```csharp
PathFigure myPathFigure = new PathFigure();
myPathFigure.StartPoint = new Point(10, 50);

LineSegment myLineSegment = new LineSegment();
myLineSegment.Point = new Point(200, 70);

PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();
myPathSegmentCollection.Add(myLineSegment);

myPathFigure.Segments = myPathSegmentCollection;

PathFigureCollection myPathFigureCollection = new PathFigureCollection();
myPathFigureCollection.Add(myPathFigure);

PathGeometry myPathGeometry = new PathGeometry();
myPathGeometry.Figures = myPathFigureCollection;

Path myPath = new Path();
myPath.Stroke = Brushes.Black;
myPath.StrokeThickness = 1;
myPath.Data = myPathGeometry;
```

```vb
Dim myPathFigure As New PathFigure()
myPathFigure.StartPoint = New Point(10, 50)

Dim myLineSegment As New LineSegment()
myLineSegment.Point = New Point(200, 70)

Dim myPathSegmentCollection As New PathSegmentCollection()
myPathSegmentCollection.Add(myLineSegment)

myPathFigure.Segments = myPathSegmentCollection

Dim myPathFigureCollection As New PathFigureCollection()
myPathFigureCollection.Add(myPathFigure)

Dim myPathGeometry As New PathGeometry()
myPathGeometry.Figures = myPathFigureCollection

Dim myPath As New Path()
myPath.Stroke = Brushes.Black
myPath.StrokeThickness = 1
myPath.Data = myPathGeometry
```

<span data-ttu-id="90aca-116">Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="90aca-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>

## <a name="see-also"></a><span data-ttu-id="90aca-117">См. также</span><span class="sxs-lookup"><span data-stu-id="90aca-117">See also</span></span>

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="90aca-118">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="90aca-118">Geometry Overview</span></span>](geometry-overview.md)
