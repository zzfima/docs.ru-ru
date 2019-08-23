---
title: Практическое руководство. Проверка попадания геометрического объекта в визуальный объект
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923383"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Практическое руководство. Проверка попадания геометрического объекта в визуальный объект
В этом примере показано, как выполнить проверку нажатия для визуального объекта, состоящего из одного или <xref:System.Windows.Media.Geometry> нескольких объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, <xref:System.Windows.Media.DrawingGroup> как получить из визуального объекта, <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> использующего метод. Затем выполняется проверка нажатия для отображаемого содержимого каждого рисунка в, <xref:System.Windows.Media.DrawingGroup> чтобы определить, какая геометрия была достигнута.  
  
> [!NOTE]
> В большинстве случаев для определения того, пересекается ли точка с отображаемым содержимым визуального элемента, используется <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Метод является перегруженным методом, который позволяет выполнять проверку попадания с помощью указанного <xref:System.Windows.Point> или <xref:System.Windows.Media.Geometry>. <xref:System.Windows.Media.Geometry.FillContains%2A> Если линия геометрического объекта штрихованная, штрих может выходить за границы заполнения. В этом случае может потребоваться вызов <xref:System.Windows.Media.Geometry.StrokeContains%2A> в дополнение к. <xref:System.Windows.Media.Geometry.FillContains%2A>  
  
 Можно также предоставить <xref:System.Windows.Media.ToleranceType> , который используется в целях спрямления Безье.  
  
> [!NOTE]
> В этом примере не учитываются преобразования или обрезка, которые могут быть применены к геометрическому объекту. Кроме того этот пример не будет работать с элементом управления со стилями, поскольку он не имеет никаких рисунков, непосредственно связанных с ним.  
  
## <a name="see-also"></a>См. также

- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
- [Проверка нажатия с использованием геометрии в качестве параметра](how-to-hit-test-using-geometry-as-a-parameter.md)
