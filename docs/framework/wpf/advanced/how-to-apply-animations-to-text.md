---
title: Практическое руководство. Применение анимаций к тексту
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174632"
---
# <a name="how-to-apply-animations-to-text"></a>Практическое руководство. Применение анимаций к тексту
Анимации могут менять отображение и внешний вид текста в приложении. В следующих примерах используются различные типы <xref:System.Windows.Controls.TextBlock> анимаций для влияния на отображение текста в элементе управления.  
  
## <a name="example"></a>Пример  
 В следующем примере используется для <xref:System.Windows.Media.Animation.DoubleAnimation> анимирования ширины текстового блока. Значение ширины за 10 секунд меняется с ширины текстового блока до 0, затем значения ширины меняются местами и анимация продолжается. Этот тип анимации создает эффект очистки.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Следующий пример <xref:System.Windows.Media.Animation.DoubleAnimation> использует для того чтобы оживить непрозрачность блока текста. Значение прозрачности меняется с 1,0 до 0 в течение 5 секунд, затем значения меняются местами и анимация продолжается.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Следующая диаграмма показывает эффект <xref:System.Windows.Controls.TextBlock> управления, изменяя `1.00` `0.00` его непрозрачность от к <xref:System.Windows.Media.Animation.Timeline.Duration%2A>во время 5-секундного интервала, определенного .  
  
 ![Текст меняет непрозрачность с 1.00 до 0.00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimation> для анимирования цвета переднего плана текстового блока. Значение основного цвета меняется с первого цвета на второй в течение 5 секунд, затем значения цвета меняются местами и анимация продолжается.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimation> используется для поворота текстового блока. Текстовый блок выполняет полный поворот за 20 секунд, а затем повторяет вращение.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md)
