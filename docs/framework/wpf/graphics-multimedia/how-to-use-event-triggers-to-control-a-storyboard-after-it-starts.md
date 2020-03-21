---
title: Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186699"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="db809-102">Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска</span><span class="sxs-lookup"><span data-stu-id="db809-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="db809-103">В этом примере <xref:System.Windows.Media.Animation.Storyboard> показано, как управлять запуском после его запуска.</span><span class="sxs-lookup"><span data-stu-id="db809-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="db809-104">Для начала <xref:System.Windows.Media.Animation.Storyboard> с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]помощью, использование <xref:System.Windows.Media.Animation.BeginStoryboard>, который распределяет анимации на объекты и свойства, которые они анимировать, а затем запускает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="db809-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="db809-105">Если вы <xref:System.Windows.Media.Animation.BeginStoryboard> даете имя, <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> указывая его свойство, вы делаете его управляемым раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="db809-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="db809-106">Затем можно интерактивно управлять раскадровки после его запуска.</span><span class="sxs-lookup"><span data-stu-id="db809-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="db809-107">Используйте следующие действия <xref:System.Windows.EventTrigger> раскадровки вместе с объектами для управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="db809-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="db809-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Паузы раскадровки.</span><span class="sxs-lookup"><span data-stu-id="db809-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="db809-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.</span><span class="sxs-lookup"><span data-stu-id="db809-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="db809-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.</span><span class="sxs-lookup"><span data-stu-id="db809-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="db809-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Продвигает раскадровку до конца периода заполнения, если он имеет один.</span><span class="sxs-lookup"><span data-stu-id="db809-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="db809-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="db809-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="db809-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку, освобождая ресурсы.</span><span class="sxs-lookup"><span data-stu-id="db809-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="db809-114">Пример</span><span class="sxs-lookup"><span data-stu-id="db809-114">Example</span></span>

<span data-ttu-id="db809-115">В следующем примере используются управляемые действия раскадровки для интерактивного управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="db809-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="db809-116">Чтобы увидеть пример управления раскадровкой с помощью кода, [см. Управление раскадровкой после того, как он начинает использовать свои интерактивные методы.](how-to-control-a-storyboard-after-it-starts.md)</span><span class="sxs-lookup"><span data-stu-id="db809-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="db809-117">Дополнительные примеры можно найти в [галерее «Пример анимации».](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)</span><span class="sxs-lookup"><span data-stu-id="db809-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="db809-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="db809-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="db809-119">Управление раскадровкой после ее запуска с помощью интерактивных методов</span><span class="sxs-lookup"><span data-stu-id="db809-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="db809-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="db809-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="db809-121">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="db809-121">Storyboards Overview</span></span>](storyboards-overview.md)
