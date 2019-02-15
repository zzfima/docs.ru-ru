---
title: Как выполнить  Задание значения свойства HandoffBehavior для анимаций раскадровки
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 9a27c377e2993c1e67ada508071698a541cec660
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305445"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="8a07c-102">Как выполнить  Задание значения свойства HandoffBehavior для анимаций раскадровки</span><span class="sxs-lookup"><span data-stu-id="8a07c-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="8a07c-103">В этом примере показано, как указать переадресуемое поведение между анимациями раскадровки.</span><span class="sxs-lookup"><span data-stu-id="8a07c-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="8a07c-104"><xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Свойство <xref:System.Windows.Media.Animation.BeginStoryboard> указывает, как новая анимация взаимодействовать с любыми существующими анимациями, уже примененные к свойству.</span><span class="sxs-lookup"><span data-stu-id="8a07c-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a07c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8a07c-105">Example</span></span>  
 <span data-ttu-id="8a07c-106">В следующем примере создается две кнопки, увеличить размер при движении курсора мыши над ними и уменьшаются при движении курсора немедленно.</span><span class="sxs-lookup"><span data-stu-id="8a07c-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="8a07c-107">Если указатель мыши на кнопку и быстро удалить курсор, вторая анимация будет применяться до завершения первого.</span><span class="sxs-lookup"><span data-stu-id="8a07c-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="8a07c-108">При перекрытии двух объектов анимации так, как можно видеть разницу между <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> значения <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> и <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="8a07c-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="8a07c-109">Значение <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> объединяет перекрывающихся анимаций, вызывая плавный переход между анимациями при значение <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> приводит к новой анимации немедленно заменить ранее перекрывающиеся анимации.</span><span class="sxs-lookup"><span data-stu-id="8a07c-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8a07c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8a07c-110">See also</span></span>
- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="8a07c-111">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="8a07c-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="8a07c-112">Анимация и расчет времени</span><span class="sxs-lookup"><span data-stu-id="8a07c-112">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="8a07c-113">Анимации и практические руководства</span><span class="sxs-lookup"><span data-stu-id="8a07c-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
