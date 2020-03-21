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
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="6c3b6-102">Практическое руководство. Применение анимаций к тексту</span><span class="sxs-lookup"><span data-stu-id="6c3b6-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="6c3b6-103">Анимации могут менять отображение и внешний вид текста в приложении.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="6c3b6-104">В следующих примерах используются различные типы <xref:System.Windows.Controls.TextBlock> анимаций для влияния на отображение текста в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c3b6-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6c3b6-105">Example</span></span>  
 <span data-ttu-id="6c3b6-106">В следующем примере используется для <xref:System.Windows.Media.Animation.DoubleAnimation> анимирования ширины текстового блока.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="6c3b6-107">Значение ширины за 10 секунд меняется с ширины текстового блока до 0, затем значения ширины меняются местами и анимация продолжается.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="6c3b6-108">Этот тип анимации создает эффект очистки.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="6c3b6-109">Следующий пример <xref:System.Windows.Media.Animation.DoubleAnimation> использует для того чтобы оживить непрозрачность блока текста.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="6c3b6-110">Значение прозрачности меняется с 1,0 до 0 в течение 5 секунд, затем значения меняются местами и анимация продолжается.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="6c3b6-111">Следующая диаграмма показывает эффект <xref:System.Windows.Controls.TextBlock> управления, изменяя `1.00` `0.00` его непрозрачность от к <xref:System.Windows.Media.Animation.Timeline.Duration%2A>во время 5-секундного интервала, определенного .</span><span class="sxs-lookup"><span data-stu-id="6c3b6-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![Текст меняет непрозрачность с 1.00 до 0.00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 <span data-ttu-id="6c3b6-113">В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimation> для анимирования цвета переднего плана текстового блока.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="6c3b6-114">Значение основного цвета меняется с первого цвета на второй в течение 5 секунд, затем значения цвета меняются местами и анимация продолжается.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="6c3b6-115">В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimation> используется для поворота текстового блока.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="6c3b6-116">Текстовый блок выполняет полный поворот за 20 секунд, а затем повторяет вращение.</span><span class="sxs-lookup"><span data-stu-id="6c3b6-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="6c3b6-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c3b6-117">See also</span></span>

- [<span data-ttu-id="6c3b6-118">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="6c3b6-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
