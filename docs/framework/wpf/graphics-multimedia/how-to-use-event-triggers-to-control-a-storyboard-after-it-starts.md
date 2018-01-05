---
title: "Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80871d9daeec257351134e9f7a72a10b697e842a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="830be-102">Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска</span><span class="sxs-lookup"><span data-stu-id="830be-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="830be-103">В этом примере показано, как управлять <xref:System.Windows.Media.Animation.Storyboard> после ее запуска.</span><span class="sxs-lookup"><span data-stu-id="830be-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="830be-104">Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard>, которая распределяет анимацию для объектов и свойств и затем запускает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="830be-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="830be-105">Если вы предоставите <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав его <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> свойства, можно упростить управляемой раскадровки.</span><span class="sxs-lookup"><span data-stu-id="830be-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="830be-106">Затем можно интерактивно управлять раскадровкой после ее запуска.</span><span class="sxs-lookup"><span data-stu-id="830be-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="830be-107">Используйте следующие действия раскадровки вместе с <xref:System.Windows.EventTrigger> объекты для управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="830be-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="830be-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Приостанавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="830be-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="830be-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.</span><span class="sxs-lookup"><span data-stu-id="830be-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="830be-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.</span><span class="sxs-lookup"><span data-stu-id="830be-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="830be-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Перемещает раскадровки в конец периода заполнения, если он есть.</span><span class="sxs-lookup"><span data-stu-id="830be-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="830be-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="830be-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="830be-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку, освобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="830be-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="830be-114">Пример</span><span class="sxs-lookup"><span data-stu-id="830be-114">Example</span></span>  
 <span data-ttu-id="830be-115">В следующем примере управляемые действия раскадровки для интерактивного управления раскадровки.</span><span class="sxs-lookup"><span data-stu-id="830be-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="830be-116">**Примечание:** пример управления раскадровки с помощью кода, см. в разделе [управления раскадровки после его запуске с помощью его интерактивных методов](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="830be-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="830be-117">Дополнительные примеры см. в разделе [Коллекция примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="830be-117">For additional examples, see the [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830be-118">См. также</span><span class="sxs-lookup"><span data-stu-id="830be-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="830be-119">Управление раскадровкой после ее запуска с помощью интерактивных методов</span><span class="sxs-lookup"><span data-stu-id="830be-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="830be-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="830be-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="830be-121">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="830be-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
