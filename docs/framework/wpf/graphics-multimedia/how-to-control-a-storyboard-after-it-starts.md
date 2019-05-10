---
title: Практическое руководство. Управление раскадровкой после ее запуска
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 680676921e14ad69d97f3ee1c39e3ec955e66dec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662143"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="acbff-102">Практическое руководство. Управление раскадровкой после ее запуска</span><span class="sxs-lookup"><span data-stu-id="acbff-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="acbff-103">В этом примере показано, как использовать код для управления <xref:System.Windows.Media.Animation.Storyboard> после ее запуска.</span><span class="sxs-lookup"><span data-stu-id="acbff-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="acbff-104">Управление раскадровкой в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], использовать <xref:System.Windows.Trigger> и <xref:System.Windows.TriggerAction> объектов; например, см. в разделе [использование триггеров событий для управления раскадровкой после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="acbff-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="acbff-105">Чтобы запустить раскадровку, используйте его <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод, который распределяет анимации раскадровки в свойства и запускает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="acbff-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="acbff-106">Чтобы сделать раскадровку управляемой, используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод и указать **true** качестве второго параметра.</span><span class="sxs-lookup"><span data-stu-id="acbff-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="acbff-107">Затем можно использовать интерактивные методы раскадровки для приостановки, возобновления, поиска, остановить, ускорить работу, или снизить скорость раскадровки или перейти к периоду заполнения.</span><span class="sxs-lookup"><span data-stu-id="acbff-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="acbff-108">Ниже приведен список интерактивных методов раскадровки:</span><span class="sxs-lookup"><span data-stu-id="acbff-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
- <span data-ttu-id="acbff-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Приостанавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="acbff-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
- <span data-ttu-id="acbff-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Возобновляет приостановленную раскадровку.</span><span class="sxs-lookup"><span data-stu-id="acbff-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
- <span data-ttu-id="acbff-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Задает интерактивную скорость раскадровки.</span><span class="sxs-lookup"><span data-stu-id="acbff-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
- <span data-ttu-id="acbff-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Ищет указанное место раскадровки.</span><span class="sxs-lookup"><span data-stu-id="acbff-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
- <span data-ttu-id="acbff-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Поиск раскадровки в указанное расположение.</span><span class="sxs-lookup"><span data-stu-id="acbff-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="acbff-114">В отличие от <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метод, эта операция обрабатывается до следующий такт.</span><span class="sxs-lookup"><span data-stu-id="acbff-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
- <span data-ttu-id="acbff-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Перемещает раскадровку к периоду заполнения, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="acbff-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
- <span data-ttu-id="acbff-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Останавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="acbff-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="acbff-117">В следующем примере несколько методов используются для интерактивного управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="acbff-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="acbff-118">**Примечание.** Чтобы ознакомиться с примером раскадровкой с помощью триггеров с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], см. в разделе [использование триггеров событий для управления раскадровкой после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="acbff-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acbff-119">Пример</span><span class="sxs-lookup"><span data-stu-id="acbff-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="acbff-120">См. также</span><span class="sxs-lookup"><span data-stu-id="acbff-120">See also</span></span>

- [<span data-ttu-id="acbff-121">Использование триггеров событий для управления раскадровкой после ее запуска</span><span class="sxs-lookup"><span data-stu-id="acbff-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
