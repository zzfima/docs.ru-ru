---
title: Практическое руководство. Управление раскадровкой после ее запуска
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855861"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="884ab-102">Практическое руководство. Управление раскадровкой после ее запуска</span><span class="sxs-lookup"><span data-stu-id="884ab-102">How to: Control a Storyboard After It Starts</span></span>

<span data-ttu-id="884ab-103">В этом примере показано, как использовать код для управления <xref:System.Windows.Media.Animation.Storyboard> после его запуска.</span><span class="sxs-lookup"><span data-stu-id="884ab-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="884ab-104">Для управления раскадровкой [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]в используйте <xref:System.Windows.Trigger> объекты <xref:System.Windows.TriggerAction> и. пример см. в разделе [Использование триггеров событий для управления раскадровкой после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="884ab-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

<span data-ttu-id="884ab-105">Для запуска раскадровки используется <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод, который распределяет анимации раскадровки по свойствам, которые они анимированы, и запускает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="884ab-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>

<span data-ttu-id="884ab-106">Чтобы сделать раскадровку управляемой, используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод и укажите **значение true** в качестве второго параметра.</span><span class="sxs-lookup"><span data-stu-id="884ab-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="884ab-107">Затем можно использовать интерактивные методы раскадровки, чтобы приостанавливать, возобновлять, искать, останавливать, ускорить или замедлить раскадровку, а также переключаться на свой период заполнения.</span><span class="sxs-lookup"><span data-stu-id="884ab-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="884ab-108">Ниже приведен список интерактивных методов раскадровки:</span><span class="sxs-lookup"><span data-stu-id="884ab-108">The following is a list of the storyboard's interactive methods:</span></span>

- <span data-ttu-id="884ab-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Приостанавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="884ab-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>

- <span data-ttu-id="884ab-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Возобновляет приостановленную раскадровку.</span><span class="sxs-lookup"><span data-stu-id="884ab-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="884ab-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Задает интерактивную скорость раскадровки.</span><span class="sxs-lookup"><span data-stu-id="884ab-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>

- <span data-ttu-id="884ab-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Выполняет поиск раскадровки в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="884ab-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>

- <span data-ttu-id="884ab-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Выполняет поиск раскадровки в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="884ab-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="884ab-114">В отличие <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> от метода, эта операция обрабатывается до следующего тика.</span><span class="sxs-lookup"><span data-stu-id="884ab-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>

- <span data-ttu-id="884ab-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Переносит раскадровку на ее период заполнения, если она есть.</span><span class="sxs-lookup"><span data-stu-id="884ab-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>

- <span data-ttu-id="884ab-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Останавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="884ab-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>

<span data-ttu-id="884ab-117">В следующем примере для интерактивного управления раскадровкой используются несколько методов раскадровки.</span><span class="sxs-lookup"><span data-stu-id="884ab-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="884ab-118">Пример управления раскадровкой с помощью триггеров с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]см. в разделе [Использование триггеров событий для контроля раскадровки после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="884ab-118">To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>

## <a name="example"></a><span data-ttu-id="884ab-119">Пример</span><span class="sxs-lookup"><span data-stu-id="884ab-119">Example</span></span>

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a><span data-ttu-id="884ab-120">См. также</span><span class="sxs-lookup"><span data-stu-id="884ab-120">See also</span></span>

- [<span data-ttu-id="884ab-121">Использование триггеров событий для управления раскадровкой после ее запуска</span><span class="sxs-lookup"><span data-stu-id="884ab-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
