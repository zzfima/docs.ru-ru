---
title: "Практическое руководство. Установка длительности анимации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8d15a1b8432b3dae5bee73396bdec9fc9d50f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="9cc80-102">Практическое руководство. Установка длительности анимации</span><span class="sxs-lookup"><span data-stu-id="9cc80-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="9cc80-103">Объект <xref:System.Windows.Media.Animation.Timeline> представляет сегмент времени и длина этого сегмента определяется по временной шкале <xref:System.Windows.Duration>.</span><span class="sxs-lookup"><span data-stu-id="9cc80-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="9cc80-104">Когда <xref:System.Windows.Media.Animation.Timeline> достигает конца его длительности воспроизведение прекращается.</span><span class="sxs-lookup"><span data-stu-id="9cc80-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="9cc80-105">Если <xref:System.Windows.Media.Animation.Timeline> имеет дочерние временные шкалы, они также останавливают воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="9cc80-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="9cc80-106">В случае анимации <xref:System.Windows.Duration> указывает, как долго анимация выполняет переход от ее начального значения до конечного.</span><span class="sxs-lookup"><span data-stu-id="9cc80-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="9cc80-107">Можно указать <xref:System.Windows.Duration> с определенным, ограниченным временем или специальные значения <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>.</span><span class="sxs-lookup"><span data-stu-id="9cc80-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="9cc80-108">Длительность анимации всегда должен иметь значение времени, поскольку анимация всегда должен иметь определенную, ограниченную длину — в противном случае анимации не узнает, как переход между заданными значениями.</span><span class="sxs-lookup"><span data-stu-id="9cc80-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="9cc80-109">Шкалы времени контейнера (<xref:System.Windows.Media.Animation.TimelineGroup> объектов), таких как <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.ParallelTimeline>, имеют длительность по умолчанию <xref:System.Windows.Duration.Automatic%2A>, то есть они автоматически завершаются после их последний дочерний элемент останавливает воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="9cc80-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="9cc80-110">В следующем примере, ширину, высоту и заполнения цвет <xref:System.Windows.Shapes.Rectangle> выполняется анимация.</span><span class="sxs-lookup"><span data-stu-id="9cc80-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="9cc80-111">Длительность, установленная для анимации или контейнера, оказывает эффекты анимации, включая управление скоростью анимации, а также путем переопределения длительность дочерние временные шкалы с длительностью контейнера временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="9cc80-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cc80-112">Пример</span><span class="sxs-lookup"><span data-stu-id="9cc80-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9cc80-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9cc80-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="9cc80-114">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="9cc80-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
