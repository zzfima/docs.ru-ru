---
title: Практическое руководство. Анимация матрицы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344920"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Практическое руководство. Анимация матрицы с помощью ключевых кадров
В этом примере показано, <xref:System.Windows.Media.MatrixTransform.Matrix%2A> как <xref:System.Windows.Media.MatrixTransform> оживить свойство элемента с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.MatrixTransform.Matrix%2A> для анимировать свойство <xref:System.Windows.Media.MatrixTransform>. Пример использует <xref:System.Windows.Media.MatrixTransform> объект для преобразования внешнего вида <xref:System.Windows.Controls.Button>и положения .  
  
 Эта анимация <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> использует класс для создания двух ключевых кадров и делает следующее с ними:  
  
1. Оживляет первое <xref:System.Windows.Media.Matrix> в течение первых 0,2 секунды. Пример изменяет <xref:System.Windows.Media.Matrix.M11%2A> <xref:System.Windows.Media.Matrix.M12%2A> свойства <xref:System.Windows.Media.Matrix>и свойства . Это изменение приводит к тому, что кнопка растягивается и становится искаженной. Пример также <xref:System.Windows.Media.Matrix.OffsetX%2A> изменяет <xref:System.Windows.Media.Matrix.OffsetY%2A> свойства так, чтобы кнопка изменяла положение.  
  
2. Оживляет второе <xref:System.Windows.Media.Matrix> место на 1,0 секунды. Кнопка перемещается в другое положение, в то время как кнопка больше не перекос или растягивается.  
  
3. Повторяет анимацию на неопределенный срок.  
  
> [!NOTE]
> Ключевые кадры, <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> получаемые из объекта, создают резкие скачки между значениями, то есть движение анимации отрывисто.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
