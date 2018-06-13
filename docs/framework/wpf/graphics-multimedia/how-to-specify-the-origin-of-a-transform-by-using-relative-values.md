---
title: Практическое руководство. Задание источника преобразования с помощью относительных значений
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: ff263af8fbedeec483eee213c07dd4ec169805de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561411"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Практическое руководство. Задание источника преобразования с помощью относительных значений
В этом примере показано использование относительных значений для указания <xref:System.Windows.UIElement.RenderTransform%2A> , применяемый к <xref:System.Windows.FrameworkElement>.  
  
 Когда поворачивать, масштабировать и наклонять <xref:System.Windows.FrameworkElement> с помощью <xref:System.Windows.UIElement.RenderTransform%2A> свойства, значение по умолчанию применяет преобразование верхнего левого угла элемента. Если требуется выполнить поворот, масштабирование или наклон в центре элемента, можно скорректировать действие, задав центр преобразования в центре элемента. Но для этого способа требуется знание размера элемента. Более простой способ применения преобразования к центру элемента является установка его <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойства (0,5, 0,5), вместо установки центрального значения преобразования.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.RotateTransform> Поворачиваемый <xref:System.Windows.Controls.Button> 45 градусов по часовой стрелке. Так как в примере не задана центральная точка, то кнопка поворачивается вокруг точки (0, 0), т. е. левого верхнего угла. <xref:System.Windows.Media.RotateTransform> Применяется к <xref:System.Windows.UIElement.RenderTransform%2A> свойство.  
  
 Ниже показан результат преобразования для следующего примера.  
  
 ![Преобразованная кнопка с использованием RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Поворот по часовой стрелке на 45 градусов с использованием свойства RenderTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 В следующем примере также используется <xref:System.Windows.Media.RotateTransform> Поворачиваемый <xref:System.Windows.Controls.Button> 45 градусов по часовой стрелке, однако в этом примере устанавливается <xref:System.Windows.UIElement.RenderTransformOrigin%2A> кнопки (0,5, 0,5). В результате кнопка поворачивается вокруг центра, а не вокруг левого верхнего угла.  
  
 Ниже показан результат преобразования для следующего примера.  
  
 ![Кнопка, преобразованная по центру](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Поворот на 45 градусов с использованием свойства RenderTransform с заданным для RenderTransformOrigin значением (0,5, 0,5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Дополнительные сведения о преобразовании <xref:System.Windows.FrameworkElement> объектов, в разделе [преобразует Обзор](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Transform>  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
