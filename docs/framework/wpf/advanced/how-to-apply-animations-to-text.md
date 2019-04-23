---
title: Практическое руководство. Применение анимаций к тексту
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 38aa432fecc5b5e10d8eb90be9c1c596728ed613
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108216"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="c78d5-102">Практическое руководство. Применение анимаций к тексту</span><span class="sxs-lookup"><span data-stu-id="c78d5-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="c78d5-103">Анимации могут менять отображение и внешний вид текста в приложении.</span><span class="sxs-lookup"><span data-stu-id="c78d5-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="c78d5-104">В следующих примерах используются различные виды анимации влияющие на отображение текста в <xref:System.Windows.Controls.TextBlock> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c78d5-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c78d5-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c78d5-105">Example</span></span>  
 <span data-ttu-id="c78d5-106">В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации ширины текстового блока.</span><span class="sxs-lookup"><span data-stu-id="c78d5-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="c78d5-107">Значение ширины за 10 секунд меняется с ширины текстового блока до 0, затем значения ширины меняются местами и анимация продолжается.</span><span class="sxs-lookup"><span data-stu-id="c78d5-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="c78d5-108">Этот тип анимации создает эффект очистки.</span><span class="sxs-lookup"><span data-stu-id="c78d5-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="c78d5-109">В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации прозрачности текстового блока.</span><span class="sxs-lookup"><span data-stu-id="c78d5-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="c78d5-110">Значение прозрачности меняется с 1,0 до 0 в течение 5 секунд, затем значения меняются местами и анимация продолжается.</span><span class="sxs-lookup"><span data-stu-id="c78d5-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="c78d5-111">В примере ниже показан эффект <xref:System.Windows.Controls.TextBlock> управления, прозрачность которого меняется с `1.00` для `0.00` во время 5-секундный интервал, определяемый <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="c78d5-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![Изменение непрозрачности текста с 1,00 до 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  
   
 <span data-ttu-id="c78d5-113">В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimation> для анимации основного цвета текстового блока.</span><span class="sxs-lookup"><span data-stu-id="c78d5-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="c78d5-114">Значение основного цвета меняется с первого цвета на второй в течение 5 секунд, затем значения цвета меняются местами и анимация продолжается.</span><span class="sxs-lookup"><span data-stu-id="c78d5-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="c78d5-115">В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для вращения текстового блока.</span><span class="sxs-lookup"><span data-stu-id="c78d5-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="c78d5-116">Текстовый блок выполняет полный поворот за 20 секунд, а затем повторяет вращение.</span><span class="sxs-lookup"><span data-stu-id="c78d5-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="c78d5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c78d5-117">See also</span></span>

- [<span data-ttu-id="c78d5-118">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="c78d5-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
