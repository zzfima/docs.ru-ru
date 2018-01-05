---
title: "Обзор фигур и базовых средств рисования в приложении WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2912215cb8fb0090cef58e0201cc355da1f0bf19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="09449-102">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="09449-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="09449-103">В этом разделе содержится обзор рисования с помощью <xref:System.Windows.Shapes.Shape> объектов.</span><span class="sxs-lookup"><span data-stu-id="09449-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="09449-104">Объект <xref:System.Windows.Shapes.Shape> — это тип <xref:System.Windows.UIElement> , позволяющий нарисовать фигуру на экране.</span><span class="sxs-lookup"><span data-stu-id="09449-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="09449-105">Так как они являются элементами пользовательского интерфейса, <xref:System.Windows.Shapes.Shape> объекты могут использоваться внутри <xref:System.Windows.Controls.Panel> элементы и элементы управления.</span><span class="sxs-lookup"><span data-stu-id="09449-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="09449-106"> предоставляет несколько уровней доступа к службам для работы с графикой и службам рендеринга.</span><span class="sxs-lookup"><span data-stu-id="09449-106"> offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="09449-107">На верхнем уровне <xref:System.Windows.Shapes.Shape> объектов просты в использовании и предоставляют множество полезных возможностей, таких как разметка и участие в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] системы событий.</span><span class="sxs-lookup"><span data-stu-id="09449-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="09449-108">Объекты фигур</span><span class="sxs-lookup"><span data-stu-id="09449-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="09449-109">предоставляет ряд готовых к использованию <xref:System.Windows.Shapes.Shape> объектов.</span><span class="sxs-lookup"><span data-stu-id="09449-109"> provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="09449-110">Все объекты фигур наследуются от <xref:System.Windows.Shapes.Shape> класса.</span><span class="sxs-lookup"><span data-stu-id="09449-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="09449-111">Доступные объекты фигур включают <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, и <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="09449-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="09449-112"><xref:System.Windows.Shapes.Shape>объекты используют следующие общие свойства.</span><span class="sxs-lookup"><span data-stu-id="09449-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
-   <span data-ttu-id="09449-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Описывает способ рисования контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
-   <span data-ttu-id="09449-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Описывает толщину контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
-   <span data-ttu-id="09449-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Описывает способ рисования внутренней области фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
-   <span data-ttu-id="09449-116">Свойства данных, определяющие координаты и вершины, измеряются в аппаратно-независимых пикселях.</span><span class="sxs-lookup"><span data-stu-id="09449-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="09449-117">Так как они являются производными от <xref:System.Windows.UIElement>, фигуры объекты могут использоваться внутри панелей и большинства элементов управления.</span><span class="sxs-lookup"><span data-stu-id="09449-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="09449-118"><xref:System.Windows.Controls.Canvas> Панель — особенно подходит для создания сложных рисунков, поскольку она поддерживает абсолютное позиционирование дочерних объектов.</span><span class="sxs-lookup"><span data-stu-id="09449-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="09449-119"><xref:System.Windows.Shapes.Line> Позволяет нарисовать линию между двумя точками.</span><span class="sxs-lookup"><span data-stu-id="09449-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="09449-120">В следующем примере показано несколько способов указания координат линии и свойств штриха.</span><span class="sxs-lookup"><span data-stu-id="09449-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="09449-121">На следующем рисунке показаны создаваемые <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="09449-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="09449-122">![Рисунок линии](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="09449-122">![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="09449-123">Несмотря на то что <xref:System.Windows.Shapes.Line> класс предоставить <xref:System.Windows.Shapes.Shape.Fill%2A> значение его свойства не оказывает влияния поскольку <xref:System.Windows.Shapes.Line> нет области.</span><span class="sxs-lookup"><span data-stu-id="09449-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="09449-124">Другой общей фигурой является <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="09449-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="09449-125">Создание <xref:System.Windows.Shapes.Ellipse> , определив фигуры <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="09449-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="09449-126">Рисование окружности, укажите <xref:System.Windows.Shapes.Ellipse> которого <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значения равны.</span><span class="sxs-lookup"><span data-stu-id="09449-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="09449-127">На рисунке показан пример отображаемого объекта <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="09449-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="09449-128">![Рисунок эллипса](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="09449-128">![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="09449-129">Использование путей и геометрических фигур</span><span class="sxs-lookup"><span data-stu-id="09449-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="09449-130"><xref:System.Windows.Shapes.Path> Позволяет рисовать кривые линии и сложные фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="09449-131">Эти кривые линии и фигуры описываются с помощью <xref:System.Windows.Media.Geometry> объектов.</span><span class="sxs-lookup"><span data-stu-id="09449-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="09449-132">Для использования <xref:System.Windows.Shapes.Path>, создании <xref:System.Windows.Media.Geometry> и использовать его для задания <xref:System.Windows.Shapes.Path> объекта <xref:System.Windows.Shapes.Path.Data%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="09449-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="09449-133">Существуют разнообразные <xref:System.Windows.Media.Geometry> объектов для выбора.</span><span class="sxs-lookup"><span data-stu-id="09449-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="09449-134"><xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, И <xref:System.Windows.Media.EllipseGeometry> классы описывают относительно простые фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="09449-135">Для создания более сложных фигур или кривых, используйте <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="09449-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="09449-136">Классы PathGeometry и PathSegment</span><span class="sxs-lookup"><span data-stu-id="09449-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="09449-137"><xref:System.Windows.Media.PathGeometry>объекты состоят из одного или нескольких <xref:System.Windows.Media.PathFigure> объектов, каждый из которых <xref:System.Windows.Media.PathFigure> представляет различные «рисунок» или фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="09449-138">Каждый <xref:System.Windows.Media.PathFigure> состоит из одного или нескольких <xref:System.Windows.Media.PathSegment> объектов, каждый из которых представляет подключенных часть фигуры или формы.</span><span class="sxs-lookup"><span data-stu-id="09449-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="09449-139">Следующие типы сегмента: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, и <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="09449-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="09449-140">В следующем примере <xref:System.Windows.Shapes.Path> используется для рисования кривой Безье второго.</span><span class="sxs-lookup"><span data-stu-id="09449-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="09449-141">На следующем рисунке показана преобразованная для просмотра фигура.</span><span class="sxs-lookup"><span data-stu-id="09449-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="09449-142">![Рисунок пути](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="09449-142">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="09449-143">Дополнительные сведения о <xref:System.Windows.Media.PathGeometry> , а другой <xref:System.Windows.Media.Geometry> классы, в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="09449-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="09449-144">Сокращенный синтаксис XAML</span><span class="sxs-lookup"><span data-stu-id="09449-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="09449-145">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], может также использовать специальный сокращенный синтаксис для описания <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="09449-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="09449-146">В следующем примере сокращенный синтаксис используется для рисования сложной фигуры.</span><span class="sxs-lookup"><span data-stu-id="09449-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="09449-147">На следующем рисунке показана представляемый <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="09449-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="09449-148">![Рисунок пути](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="09449-148">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="09449-149"><xref:System.Windows.Shapes.Path.Data%2A> Атрибут строка начинается с помощью команды «moveto» обозначается M, задающей начальную точку для пути в системе координат <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="09449-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="09449-150"><xref:System.Windows.Shapes.Path>данные параметры зависят от регистра.</span><span class="sxs-lookup"><span data-stu-id="09449-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="09449-151">Заглавная буква M указывает абсолютное положение новой текущей точки.</span><span class="sxs-lookup"><span data-stu-id="09449-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="09449-152">Строчная буква m указывала бы относительные координаты.</span><span class="sxs-lookup"><span data-stu-id="09449-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="09449-153">Первый сегмент представляет собой кубическую кривую Безье, которая начинается в точке (100, 200) и заканчивается в точке (400, 175). Эта кривая нарисована с помощью двух контрольных точек (100, 25) и (400, 350).</span><span class="sxs-lookup"><span data-stu-id="09449-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="09449-154">Этот сегмент определен командой C в <xref:System.Windows.Shapes.Path.Data%2A> строке атрибута.</span><span class="sxs-lookup"><span data-stu-id="09449-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="09449-155">Опять же, заглавная буква C указывает абсолютный путь; строчная буква c указывает относительный путь.</span><span class="sxs-lookup"><span data-stu-id="09449-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="09449-156">Второй сегмент начинается с команды lineto H, которая рисует горизонтальную линию от предыдущей точки пути (400, 175) до новой точки (280, 175).</span><span class="sxs-lookup"><span data-stu-id="09449-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="09449-157">Поскольку это команда горизонтали «lineto", указанное значение является *x*-координации.</span><span class="sxs-lookup"><span data-stu-id="09449-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="09449-158">Полный синтаксис пути, в разделе <xref:System.Windows.Shapes.Path.Data%2A> ссылку и [создать фигуру с помощью объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="09449-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="09449-159">Заполнение фигур</span><span class="sxs-lookup"><span data-stu-id="09449-159">Painting Shapes</span></span>  
 <span data-ttu-id="09449-160"><xref:System.Windows.Media.Brush>объекты используются для заливки фигуры <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="09449-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="09449-161">В следующем примере, обводки и заполнения <xref:System.Windows.Shapes.Ellipse> указаны.</span><span class="sxs-lookup"><span data-stu-id="09449-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="09449-162">Обратите внимание, что значения свойств кисти могут задаваться только в формате ключевого слова или шестнадцатеричного значения цвета.</span><span class="sxs-lookup"><span data-stu-id="09449-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="09449-163">Дополнительные сведения о доступных ключевых словах цветов см. в разделе свойств <xref:System.Windows.Media.Colors> класса в <xref:System.Windows.Media> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="09449-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```  
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="09449-164">На следующем рисунке показаны создаваемые <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="09449-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="09449-165">![Эллипс](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="09449-165">![An ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="09449-166">Кроме того, можно использовать синтаксис элемента свойства для явного создания <xref:System.Windows.Media.SolidColorBrush> объекта для заливки фигуры сплошным цветом.</span><span class="sxs-lookup"><span data-stu-id="09449-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```  
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="09449-167">На рисунке ниже показана фигура, преобразованная для просмотра.</span><span class="sxs-lookup"><span data-stu-id="09449-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="09449-168">![Иллюстрация SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="09449-168">![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="09449-169">Для заполнения фигуры также можно использовать штриховку, градиенты, изображения, шаблоны и многое другое.</span><span class="sxs-lookup"><span data-stu-id="09449-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="09449-170">Дополнительные сведения см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="09449-170">For more information, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="09449-171">Растягиваемые фигуры</span><span class="sxs-lookup"><span data-stu-id="09449-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="09449-172"><xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, И <xref:System.Windows.Shapes.Rectangle> классы имеют <xref:System.Windows.Shapes.Shape.Stretch%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="09449-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="09449-173">Это свойство определяет, каким образом <xref:System.Windows.Shapes.Shape> содержимое объекта (рисуемой фигуры) растягивается на всю <xref:System.Windows.Shapes.Shape> пространства макета объекта.</span><span class="sxs-lookup"><span data-stu-id="09449-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="09449-174">Объект <xref:System.Windows.Shapes.Shape> пространства макета объекта — это объем пространства <xref:System.Windows.Shapes.Shape> выделяется системы макета, из-за либо явно <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> параметр или из-за его <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="09449-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="09449-175">Дополнительные сведения о макете в Windows Presentation Foundation см. в разделе [макета](../../../../docs/framework/wpf/advanced/layout.md) Обзор.</span><span class="sxs-lookup"><span data-stu-id="09449-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../../../../docs/framework/wpf/advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="09449-176">Свойство Stretch принимает одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="09449-176">The Stretch property takes one of the following values:</span></span>  
  
-   <span data-ttu-id="09449-177"><xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Не растягивается содержимое объекта.</span><span class="sxs-lookup"><span data-stu-id="09449-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
-   <span data-ttu-id="09449-178"><xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягиваются для заполнения пространства макета.</span><span class="sxs-lookup"><span data-stu-id="09449-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="09449-179">Пропорции не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="09449-179">Aspect ratio is not preserved.</span></span>  
  
-   <span data-ttu-id="09449-180"><xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается настолько, насколько это возможно для заполнения пространства макета, сохраняя исходные пропорции.</span><span class="sxs-lookup"><span data-stu-id="09449-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
-   <span data-ttu-id="09449-181"><xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Содержимое объекта растягивается до полного заполнения пространства макета, сохраняя исходные пропорции.</span><span class="sxs-lookup"><span data-stu-id="09449-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="09449-182">Обратите внимание, что при <xref:System.Windows.Shapes.Shape> растягивается содержимое объекта, <xref:System.Windows.Shapes.Shape> после растягивания рисования контура объекта.</span><span class="sxs-lookup"><span data-stu-id="09449-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="09449-183">В следующем примере <xref:System.Windows.Shapes.Polygon> используется для рисования очень маленький треугольник от (0,0) (0,1) и (1,1).</span><span class="sxs-lookup"><span data-stu-id="09449-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="09449-184"><xref:System.Windows.Shapes.Polygon> Объекта <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> установите значение 100, и ее stretch задано значение Fill.</span><span class="sxs-lookup"><span data-stu-id="09449-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="09449-185">В результате <xref:System.Windows.Shapes.Polygon> содержимое объекта (треугольник) растягивается для заполнения большего пространства.</span><span class="sxs-lookup"><span data-stu-id="09449-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```  
...  
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
...  
```  
  
```  
...  
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
...  
```  
  
<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="09449-186">Преобразование фигур</span><span class="sxs-lookup"><span data-stu-id="09449-186">Transforming Shapes</span></span>  
 <span data-ttu-id="09449-187"><xref:System.Windows.Media.Transform> Класс предоставляет средства для преобразования фигур на двумерной плоскости.</span><span class="sxs-lookup"><span data-stu-id="09449-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="09449-188">Различные типы преобразования включают поворот (<xref:System.Windows.Media.RotateTransform>), масштабирование (<xref:System.Windows.Media.ScaleTransform>), отклонение (<xref:System.Windows.Media.SkewTransform>) и преобразование (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="09449-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="09449-189">Распространенным преобразованием фигуры является поворот.</span><span class="sxs-lookup"><span data-stu-id="09449-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="09449-190">Чтобы повернуть фигуру, создайте <xref:System.Windows.Media.RotateTransform> и укажите его <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span><span class="sxs-lookup"><span data-stu-id="09449-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="09449-191"><xref:System.Windows.Media.RotateTransform.Angle%2A> 45 поворачивает элемент на 45 градусов по часовой стрелке; угол 90 поворачивает элемент на 90 градусов по часовой стрелке; и т. д.</span><span class="sxs-lookup"><span data-stu-id="09449-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="09449-192">Задать <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства, если вы хотите точки, о котором поворачивать элемент управления.</span><span class="sxs-lookup"><span data-stu-id="09449-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="09449-193">Эти значения свойств выражаются в системе координат преобразуемого элемента.</span><span class="sxs-lookup"><span data-stu-id="09449-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="09449-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A>и <xref:System.Windows.Media.RotateTransform.CenterY%2A> имеют значения по умолчанию равно нулю.</span><span class="sxs-lookup"><span data-stu-id="09449-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="09449-195">Наконец, примените <xref:System.Windows.Media.RotateTransform> к элементу.</span><span class="sxs-lookup"><span data-stu-id="09449-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="09449-196">Если вы не хотите преобразование влияет на макет, задайте фигуры <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="09449-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="09449-197">В следующем примере <xref:System.Windows.Media.RotateTransform> используется для поворота фигуры 45 градусов относительно верхнего левого угла фигуры (0,0).</span><span class="sxs-lookup"><span data-stu-id="09449-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="09449-198">В следующем примере другая фигура поворачивается на 45 градусов, но на этот раз — вокруг точки (25, 50).</span><span class="sxs-lookup"><span data-stu-id="09449-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="09449-199">На следующем рисунке показаны результаты двух преобразований.</span><span class="sxs-lookup"><span data-stu-id="09449-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="09449-200">![Поворот на 45 градусов вокруг различных точек](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="09449-200">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="09449-201">В предыдущих примерах к каждому объекту фигуры применяется одно преобразование.</span><span class="sxs-lookup"><span data-stu-id="09449-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="09449-202">Чтобы применить несколько преобразований к фигуре (или любой другой элемент пользовательского интерфейса), используйте <xref:System.Windows.Media.TransformGroup>.</span><span class="sxs-lookup"><span data-stu-id="09449-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09449-203">См. также</span><span class="sxs-lookup"><span data-stu-id="09449-203">See Also</span></span>  
 [<span data-ttu-id="09449-204">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="09449-204">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="09449-205">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="09449-205">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="09449-206">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="09449-206">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="09449-207">Пошаговое руководство. Создание первого классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="09449-207">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [<span data-ttu-id="09449-208">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="09449-208">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
