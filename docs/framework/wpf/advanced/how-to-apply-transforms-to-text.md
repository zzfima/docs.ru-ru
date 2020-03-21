---
title: Как применить преобразования к тексту
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141618"
---
# <a name="how-to-apply-transforms-to-text"></a>Как применить преобразования к тексту
Преобразования могут менять отображение текста в приложении. В следующих примерах используются различные типы преобразований визуализации, чтобы повлиять на отображение текста в элементе <xref:System.Windows.Controls.TextBlock> управления.  
  
## <a name="example"></a>Пример  
 В следующем примере показан текст, повернутый относительно заданной точки в двухмерной плоскости x-y.  
  
 ![Текст, повернутый с использованием RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 В следующем примере <xref:System.Windows.Media.RotateTransform> кода используется для вращения текста. Значение <xref:System.Windows.Media.RotateTransform.Angle%2A> 90 вращает элемент на 90 градусов по часовой стрелке.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 В следующем примере показаны вторая строка текста, масштабированная на 150 % вдоль оси X, и третья строка текста, масштабированная на 150 % вдоль оси Y.  
  
 ![Текст, масштабируемый с использованием ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 В следующем примере <xref:System.Windows.Media.ScaleTransform> кода используется для масштабирования текста от его исходного размера.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> Масштабирование текста не равнозначно увеличению шрифта текста. Размеры шрифта рассчитываются независимо друг от друга, чтобы обеспечить оптимальное разрешение для разных размеров. В масштабированном тексте, с другой стороны, сохранены пропорции текста исходного размера.  
  
 В следующем примере показан текст, наклоненный вдоль оси X.  
  
 ![Текст, искаженный с использованием SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 В следующем примере <xref:System.Windows.Media.SkewTransform> кода используется для искажая текст. Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат. В этом примере две текстовые строки, наклоненные на –30° и 30° вдоль оси X.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 В следующем примере показан текст, преобразованный (или перемещенный) вдоль осей X и Y.  
  
 ![Смещение текста с использованием TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 В следующем примере <xref:System.Windows.Media.TranslateTransform> кода используется для смещения текста. В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> Предоставляет <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> богатый набор функций для обеспечения эффектов теней. Для получения дополнительной информации смотрите [Создать текст с тенью](how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>См. также раздел

- [Применение анимаций к тексту](how-to-apply-animations-to-text.md)
