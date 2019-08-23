---
title: Практическое руководство. Анимация матрицы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963029"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Практическое руководство. Анимация матрицы с помощью ключевых кадров
В этом примере показано <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform> , как анимировать свойство объекта с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> класс используется для <xref:System.Windows.Media.MatrixTransform.Matrix%2A> анимации свойства объекта <xref:System.Windows.Media.MatrixTransform>. В примере используется <xref:System.Windows.Media.MatrixTransform> объект для преобразования внешнего вида и расположения <xref:System.Windows.Controls.Button>объекта.  
  
 Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> класс для создания двух ключевых кадров и выполняет следующие действия.  
  
1. Выполняет анимацию первой <xref:System.Windows.Media.Matrix> в течение первых 0,2 секунд. В этом примере изменяются <xref:System.Windows.Media.Matrix.M11%2A> свойства и <xref:System.Windows.Media.Matrix> <xref:System.Windows.Media.Matrix.M12%2A> объекта. Это изменение приводит к тому, что кнопка растягивается и становится неравномерной. В этом примере также изменяются <xref:System.Windows.Media.Matrix.OffsetX%2A> свойства и <xref:System.Windows.Media.Matrix.OffsetY%2A> , чтобы кнопка изменила расположение.  
  
2. Анимируется секунды <xref:System.Windows.Media.Matrix> в 1,0 секунд. Кнопка перемещается в другую точку, пока кнопка больше не наклонена или не растягивается.  
  
3. Повтор анимации в течение неограниченного времени.  
  
> [!NOTE]
> Ключевые кадры, производные от <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> объекта, создают резкие переходы между значениями, то есть перемещение анимации жерки.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
