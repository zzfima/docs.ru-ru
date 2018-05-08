---
title: Практическое руководство. Применение анимаций к тексту
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 56a12ca915cc320619a094df38d118eabf202734
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-animations-to-text"></a>Практическое руководство. Применение анимаций к тексту
Анимации могут менять отображение и внешний вид текста в приложении. В следующих примерах используется различные виды анимации, влияющие на отображение текста в <xref:System.Windows.Controls.TextBlock> элемента управления.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации ширины блока текста. Значение ширины за 10 секунд меняется с ширины текстового блока до 0, затем значения ширины меняются местами и анимация продолжается. Этот тип анимации создает эффект очистки.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> анимация непрозрачности блока текста. Значение прозрачности меняется с 1,0 до 0 в течение 5 секунд, затем значения меняются местами и анимация продолжается.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 На следующей диаграмме показан эффект <xref:System.Windows.Controls.TextBlock> изменение непрозрачности из элемента управления `1.00` для `0.00` во время 5-секундный интервал, заданный <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Изменение непрозрачности текста с 1,00 до 0,00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Изменение прозрачности текста с 1,00 до 0,00  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimation> анимация цвета переднего плана текстового блока. Значение основного цвета меняется с первого цвета на второй в течение 5 секунд, затем значения цвета меняются местами и анимация продолжается.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> изменение текстового блока. Текстовый блок выполняет полный поворот за 20 секунд, а затем повторяет вращение.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
