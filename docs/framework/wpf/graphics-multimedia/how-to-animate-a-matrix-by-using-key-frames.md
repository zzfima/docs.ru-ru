---
title: Практическое руководство. Анимация матрицы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 2c33fa1ebb3c9dd4f05c24db9de42ff47c84f983
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370583"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Практическое руководство. Анимация матрицы с помощью ключевых кадров
В этом примере демонстрируется анимация <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform> с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform>. В примере используется <xref:System.Windows.Media.MatrixTransform> объект для преобразования его внешний вид и расположение <xref:System.Windows.Controls.Button>.  
  
 Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> класса для создания двух ключевых кадров и выполняет следующие операции с ними:  
  
1.  Анимирует первый <xref:System.Windows.Media.Matrix> во время первого 0,2 секунды. В примере изменяется <xref:System.Windows.Media.Matrix.M11%2A> и <xref:System.Windows.Media.Matrix.M12%2A> свойства <xref:System.Windows.Media.Matrix>. Это изменение вызовет кнопку, чтобы растянуть и стать неравномерным. В примере также изменяется <xref:System.Windows.Media.Matrix.OffsetX%2A> и <xref:System.Windows.Media.Matrix.OffsetY%2A> свойства таким образом, изменяется положение кнопки.  
  
2.  Анимация второго <xref:System.Windows.Media.Matrix> при 1,0 секунде. Кнопка перемещается в другую должность, хотя кнопки больше не наклонен или растягивается.  
  
3.  Циклическое повторение анимации.  
  
> [!NOTE]
>  Ключевые кадры, которые являются производными от <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> объекта, создают скачкообразные переходы между значениями, то есть перемещение анимация выполняется рывками.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
