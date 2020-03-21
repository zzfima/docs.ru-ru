---
title: Практическое руководство. Масштабирование элемента
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112054"
---
# <a name="how-to-scale-an-element"></a>Практическое руководство. Масштабирование элемента
В этом примере <xref:System.Windows.Media.ScaleTransform> показано, как использовать элемент для масштабирования.  
  
 Используйте <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> и свойства для изобрагивания элемента по указанному фактору. Например, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> значение 1,5 растягивает элемент до 150 процентов от его первоначальной ширины. Значение <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 0,5 сжимает высоту элемента на 50 процентов.  
  
 Используйте <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> и свойства, чтобы указать точку, которая является центром операции масштаба. По умолчанию <xref:System.Windows.Media.ScaleTransform> a центрируется в точке (0,0), что соответствует верхнему левому углу прямоугольника. Это приводит к перемещению элемента, а также к тому, чтобы он казался больше, потому что при <xref:System.Windows.Media.Transform>применении, вы изменяете пространство координат, в котором находится объект.  
  
 В следующем примере используется удвоение <xref:System.Windows.Media.ScaleTransform> размера 50 <xref:System.Windows.Shapes.Rectangle>на 50 . Имеет <xref:System.Windows.Media.ScaleTransform> значение 0 (по умолчанию) <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>для обоих и .  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Как правило, <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> вы устанавливаете и к центру<xref:System.Windows.FrameworkElement.Width%2A>объекта, <xref:System.Windows.FrameworkElement.Height%2A>который масштабируется: ( /2, /2).  
  
 Следующий пример <xref:System.Windows.Shapes.Rectangle> показывает другой, который удваивается в размерах; однако, <xref:System.Windows.Media.ScaleTransform> это имеет значение 25 для обоих <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и, <xref:System.Windows.Media.ScaleTransform.CenterY%2A>которое соответствует к центру прямоугольника.  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Следующая иллюстрация показывает разницу между двумя <xref:System.Windows.Media.ScaleTransform> операциями. Пунктирная линия показывает размер и положение прямоугольника до масштабирования.  
  
 ![Двукратное масштабирование с разными центральными точками](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Две операции ScaleTransform с одинаковыми значениями свойств ScaleX и ScaleY, но с разными центрами  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Общие сведения о классах Transform](transforms-overview.md)
- [Как-к темам](transformations-how-to-topics.md)
