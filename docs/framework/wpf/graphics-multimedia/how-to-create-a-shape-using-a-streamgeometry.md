---
title: Практическое руководство. Создание фигуры с помощью объекта StreamGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: fd191e4cfdfa33c144389d4871a9641e9c811ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054579"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="1bc60-102">Практическое руководство. Создание фигуры с помощью объекта StreamGeometry</span><span class="sxs-lookup"><span data-stu-id="1bc60-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="1bc60-103"><xref:System.Windows.Media.StreamGeometry> — Упрощенная альтернатива <xref:System.Windows.Media.PathGeometry> для создания геометрических фигур.</span><span class="sxs-lookup"><span data-stu-id="1bc60-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="1bc60-104">Используйте <xref:System.Windows.Media.StreamGeometry> для описания сложной геометрии, но не требуется поддержка привязки данных, анимации или изменения.</span><span class="sxs-lookup"><span data-stu-id="1bc60-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="1bc60-105">Например, из-за своей эффективности <xref:System.Windows.Media.StreamGeometry> класс хорошо подходит для описания графических элементов.</span><span class="sxs-lookup"><span data-stu-id="1bc60-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bc60-106">Пример</span><span class="sxs-lookup"><span data-stu-id="1bc60-106">Example</span></span>  
 <span data-ttu-id="1bc60-107">В следующем примере синтаксис атрибутов для создания треугольного <xref:System.Windows.Media.StreamGeometry> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bc60-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="1bc60-108">Дополнительные сведения о <xref:System.Windows.Media.StreamGeometry> синтаксис атрибута, см. в разделе [синтаксис разметки пути](path-markup-syntax.md) страницы.</span><span class="sxs-lookup"><span data-stu-id="1bc60-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bc60-109">Пример</span><span class="sxs-lookup"><span data-stu-id="1bc60-109">Example</span></span>  
 <span data-ttu-id="1bc60-110">В следующем примере используется <xref:System.Windows.Media.StreamGeometry> для определения треугольника в коде.</span><span class="sxs-lookup"><span data-stu-id="1bc60-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="1bc60-111">Во-первых, в примере создается <xref:System.Windows.Media.StreamGeometry>, затем получает <xref:System.Windows.Media.StreamGeometryContext> и использует его для описания треугольника.</span><span class="sxs-lookup"><span data-stu-id="1bc60-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="1bc60-112">Пример</span><span class="sxs-lookup"><span data-stu-id="1bc60-112">Example</span></span>  
 <span data-ttu-id="1bc60-113">В следующем примере создается метод, который использует <xref:System.Windows.Media.StreamGeometry> и <xref:System.Windows.Media.StreamGeometryContext> для определения геометрической фигуры на основе указанных параметров.</span><span class="sxs-lookup"><span data-stu-id="1bc60-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1bc60-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1bc60-114">See also</span></span>

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="1bc60-115">Создание фигуры с помощью объекта PathGeometry</span><span class="sxs-lookup"><span data-stu-id="1bc60-115">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="1bc60-116">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="1bc60-116">Geometry Overview</span></span>](geometry-overview.md)
