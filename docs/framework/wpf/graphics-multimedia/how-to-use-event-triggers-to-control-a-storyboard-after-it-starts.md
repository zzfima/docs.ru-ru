---
title: Практическое руководство. Использование триггеров событий для управления раскадровкой после ее запуска
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170655"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="5c130-102">Практическое руководство. Использование триггеров событий для управления раскадровкой после ее запуска</span><span class="sxs-lookup"><span data-stu-id="5c130-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="5c130-103">В этом примере показано, как управлять <xref:System.Windows.Media.Animation.Storyboard> после ее запуска.</span><span class="sxs-lookup"><span data-stu-id="5c130-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="5c130-104">Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], использовать <xref:System.Windows.Media.Animation.BeginStoryboard>, которая распределяет анимации объектов и свойств и затем запускает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="5c130-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="5c130-105">Если вы предоставите <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав его <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> свойство, можно упростить управляемой раскадровки.</span><span class="sxs-lookup"><span data-stu-id="5c130-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="5c130-106">Вы можете затем интерактивно управлять раскадровкой после ее запуска.</span><span class="sxs-lookup"><span data-stu-id="5c130-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="5c130-107">Используйте следующие действия раскадровки вместе с <xref:System.Windows.EventTrigger> объектов для управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="5c130-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard><span data-ttu-id="5c130-108">: Приостанавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="5c130-108">: Pauses the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard><span data-ttu-id="5c130-109">: Возобновляет приостановленную раскадровку.</span><span class="sxs-lookup"><span data-stu-id="5c130-109">: Resumes a paused storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio><span data-ttu-id="5c130-110">: Изменяет скорость раскадровки.</span><span class="sxs-lookup"><span data-stu-id="5c130-110">: Changes the storyboard speed.</span></span>  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill><span data-ttu-id="5c130-111">: Перемещает раскадровку в конец ее периода заполнения, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="5c130-111">: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard><span data-ttu-id="5c130-112">: Останавливает раскадровку.</span><span class="sxs-lookup"><span data-stu-id="5c130-112">: Stops the storyboard.</span></span>  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard><span data-ttu-id="5c130-113">: Удаляет раскадровку, освобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="5c130-113">: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c130-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5c130-114">Example</span></span>  
 <span data-ttu-id="5c130-115">В следующем примере действий для управляемой раскадровки для интерактивного управления раскадровкой.</span><span class="sxs-lookup"><span data-stu-id="5c130-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="5c130-116">**Примечание.** Пример управления раскадровкой с помощью кода, см. в разделе [управления раскадровки после он начинается с помощью его интерактивных методов](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="5c130-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="5c130-117">Дополнительные примеры см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="5c130-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c130-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5c130-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="5c130-119">Управление раскадровкой после ее запуска с помощью интерактивных методов</span><span class="sxs-lookup"><span data-stu-id="5c130-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="5c130-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="5c130-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="5c130-121">Общие сведения о Storyboard</span><span class="sxs-lookup"><span data-stu-id="5c130-121">Storyboards Overview</span></span>](storyboards-overview.md)
