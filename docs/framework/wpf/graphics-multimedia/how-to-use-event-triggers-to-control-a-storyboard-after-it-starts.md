---
title: Практическое руководство. Использование триггеров событий для управления раскадровкой после ее запуска
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855851"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="89161-102">Практическое руководство. Использование триггеров событий для управления раскадровкой после ее запуска</span><span class="sxs-lookup"><span data-stu-id="89161-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="89161-103">В этом примере показано, <xref:System.Windows.Media.Animation.Storyboard> как управлять после запуска.</span><span class="sxs-lookup"><span data-stu-id="89161-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="89161-104">Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard>, который распространяет анимации на объекты и свойства, которые они анимированы, а затем запускает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="89161-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="89161-105">Если вы придаете <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> его свойство, вы сделаете его управляемой раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="89161-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="89161-106">Затем можно интерактивно управлять раскадровкой после ее запуска.</span><span class="sxs-lookup"><span data-stu-id="89161-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="89161-107">Используйте следующие действия раскадровки вместе <xref:System.Windows.EventTrigger> с объектами для управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="89161-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="89161-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Приостанавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="89161-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="89161-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.</span><span class="sxs-lookup"><span data-stu-id="89161-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="89161-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.</span><span class="sxs-lookup"><span data-stu-id="89161-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="89161-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Перемещает раскадровку в конец периода заполнения, если он имеет значение.</span><span class="sxs-lookup"><span data-stu-id="89161-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="89161-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="89161-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="89161-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку, освобождая ресурсы.</span><span class="sxs-lookup"><span data-stu-id="89161-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="89161-114">Пример</span><span class="sxs-lookup"><span data-stu-id="89161-114">Example</span></span>

<span data-ttu-id="89161-115">В следующем примере используются управляемые действия раскадровки для интерактивного управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="89161-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="89161-116">Пример управления раскадровкой с помощью кода см. в разделе [Управление раскадровкой после ее запуска с помощью интерактивных методов](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="89161-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="89161-117">Дополнительные примеры см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="89161-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

## <a name="see-also"></a><span data-ttu-id="89161-118">См. также</span><span class="sxs-lookup"><span data-stu-id="89161-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="89161-119">Управление раскадровкой после ее запуска с помощью интерактивных методов</span><span class="sxs-lookup"><span data-stu-id="89161-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="89161-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="89161-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="89161-121">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="89161-121">Storyboards Overview</span></span>](storyboards-overview.md)
