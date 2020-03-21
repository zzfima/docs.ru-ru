---
title: Практическое руководство. Вращение объекта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112067"
---
# <a name="how-to-rotate-an-object"></a>Практическое руководство. Вращение объекта
В данном примере показано, как можно вращать объект. Пример сначала создает, <xref:System.Windows.Media.RotateTransform> а затем определяет <xref:System.Windows.Media.RotateTransform.Angle%2A> его в градусах.  
  
 Следующий пример поворачивает <xref:System.Windows.Shapes.Polyline> объект на 45 градусов вокруг его верхнего левого угла.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 И <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства <xref:System.Windows.Media.RotateTransform> указывают точку, о которой вращается объект. Это центральная точка выражается в пространстве координат преобразуемого элемента. По умолчанию поворот выполняется относительно точки (0,0), которая является верхним левым углом объекта для преобразования.  
  
 Следующий пример поворачивает <xref:System.Windows.Shapes.Polyline> объект по часовой стрелке на 45 градусов вокруг точки (25,50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 На следующей иллюстрации показаны <xref:System.Windows.Media.Transform> результаты применения к двум объектам.  
  
 ![Повороты на 45 градусов с разными центральными точками](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Два объекта, повернутые на 45 градусов, с разными центрами вращения  
  
 В <xref:System.Windows.Shapes.Polyline> предыдущих примерах <xref:System.Windows.UIElement>является . При подаче <xref:System.Windows.Media.Transform> заявления <xref:System.Windows.UIElement.RenderTransform%2A> на <xref:System.Windows.UIElement>свойство объекта <xref:System.Windows.UIElement.RenderTransformOrigin%2A> можно использовать свойство <xref:System.Windows.Media.Transform> для указания происхождения для каждого, что вы применяете к элементу. Поскольку <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойство использует относительные координаты, можно применить преобразование к центру элемента, даже если вы не знаете его размер. Для получения дополнительной информации и, например, [см.](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Transform>
- [Общие сведения о классах Transform](transforms-overview.md)
- [Как-к темам](transformations-how-to-topics.md)
