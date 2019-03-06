---
title: Практическое руководство. Геометрия проверки нажатия в визуальном объекте
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: e51dd73a65666ffee5958325079e8f06f13ac61b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363804"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Практическое руководство. Геометрия проверки нажатия в визуальном объекте
В этом примере показано, как выполнить проверку попадания для визуального объекта, который состоит из одного или нескольких <xref:System.Windows.Media.Geometry> объектов.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить <xref:System.Windows.Media.DrawingGroup> из визуальный объект, который использует <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> метод. Затем выполняется попадания на отображаемом содержимом каждого рисунка в <xref:System.Windows.Media.DrawingGroup> для определения, какой геометрический объект произошло попадание.  
  
> [!NOTE]
>  В большинстве случаев можно использовать <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод для определения попадания курсора на любой из отображаемого содержимого визуального элемента.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A> Это перегруженный метод, позволяющий попадания с использованием указанного <xref:System.Windows.Point> или <xref:System.Windows.Media.Geometry>. Если линия геометрического объекта штрихованная, штрих может выходить за границы заполнения. В этом случае необходимо вызвать <xref:System.Windows.Media.Geometry.StrokeContains%2A> в дополнение к <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 Вы также можете предоставить <xref:System.Windows.Media.ToleranceType> , используемый в целях спрямления кривой Безье.  
  
> [!NOTE]
>  В этом примере не учитываются преобразования или обрезка, которые могут быть применены к геометрическому объекту. Кроме того этот пример не будет работать с элементом управления со стилями, поскольку он не имеет никаких рисунков, непосредственно связанных с ним.  
  
## <a name="see-also"></a>См. также
- [Проверка нажатия на визуальном уровне](hit-testing-in-the-visual-layer.md)
- [Проверка нажатия с использованием геометрии в качестве параметра](how-to-hit-test-using-geometry-as-a-parameter.md)
