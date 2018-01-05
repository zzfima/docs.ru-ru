---
title: "Практическое руководство. Реализация класса PriorityBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13b254867200897acad2868e396d152a5f9efcbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="2e476-102">Практическое руководство. Реализация класса PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="2e476-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="2e476-103"><xref:System.Windows.Data.PriorityBinding>в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] работает путем указания списка привязок.</span><span class="sxs-lookup"><span data-stu-id="2e476-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="2e476-104">Список привязок упорядочен от наивысшего приоритета к более низкому приоритету.</span><span class="sxs-lookup"><span data-stu-id="2e476-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="2e476-105">Если привязка наивысшего приоритета возвращает значение успешно при его обработке то нет необходимости обрабатывать другие привязки в списке.</span><span class="sxs-lookup"><span data-stu-id="2e476-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="2e476-106">Он может случиться, что привязка наивысшего приоритета занимает много времени для оценки, будет использоваться следующий высокий приоритет, успешно возвращает значение, до привязки с более высоким приоритетом успешно возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="2e476-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e476-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2e476-107">Example</span></span>  
 <span data-ttu-id="2e476-108">Чтобы продемонстрировать, как <xref:System.Windows.Data.PriorityBinding> работает, `AsyncDataSource` объект был создан со следующими тремя свойствами: `FastDP`, `SlowerDP`, и `SlowestDP`.</span><span class="sxs-lookup"><span data-stu-id="2e476-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="2e476-109">Метод доступа get `FastDP` возвращает значение `_fastDP` члена данных.</span><span class="sxs-lookup"><span data-stu-id="2e476-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="2e476-110">Метод доступа get `SlowerDP` ожидает в течение 3 секунд перед возвратом значения `_slowerDP` элемента данных.</span><span class="sxs-lookup"><span data-stu-id="2e476-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="2e476-111">Метод доступа get `SlowestDP` ожидает 5 секунд перед возвратом значения `_slowestDP` элемента данных.</span><span class="sxs-lookup"><span data-stu-id="2e476-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e476-112">Данный пример является исключительно для демонстрационных целей.</span><span class="sxs-lookup"><span data-stu-id="2e476-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="2e476-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Правила рекомендованы для определения свойств, которые являются порядков медленнее, чем мог бы быть набор полей.</span><span class="sxs-lookup"><span data-stu-id="2e476-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="2e476-114">Дополнительные сведения см. в разделе [NIB: Выбор между свойствами и методами](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span><span class="sxs-lookup"><span data-stu-id="2e476-114">For more information, see [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="2e476-115"><xref:System.Windows.Controls.TextBlock.Text%2A> Связывается в указанное свойство `AsyncDS` с помощью <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="2e476-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="2e476-116">Когда обработчик привязки обрабатывает <xref:System.Windows.Data.Binding> объектов, он начинает с первой <xref:System.Windows.Data.Binding>, который привязан к `SlowestDP` свойство.</span><span class="sxs-lookup"><span data-stu-id="2e476-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="2e476-117">Если это <xref:System.Windows.Data.Binding> — обработки, она не успешного возвращения значения, так как он находится в спящем режиме для 5 секунд, поэтому следующего <xref:System.Windows.Data.Binding> обработки элемента.</span><span class="sxs-lookup"><span data-stu-id="2e476-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="2e476-118">Следующий <xref:System.Windows.Data.Binding> не успешного возвращения значения, так как он находится в спящем режиме в течение 3 секунд.</span><span class="sxs-lookup"><span data-stu-id="2e476-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="2e476-119">Затем обработчик привязки перемещается к следующему <xref:System.Windows.Data.Binding> элемент, который привязан к `FastDP` свойство.</span><span class="sxs-lookup"><span data-stu-id="2e476-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="2e476-120">Это <xref:System.Windows.Data.Binding> возвращает значение «Fast Value».</span><span class="sxs-lookup"><span data-stu-id="2e476-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="2e476-121"><xref:System.Windows.Controls.TextBlock> Теперь отображается значение «Fast Value».</span><span class="sxs-lookup"><span data-stu-id="2e476-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="2e476-122">По прошествии 3 секунд `SlowerDP` свойство возвращает значение «Медленнее значение».</span><span class="sxs-lookup"><span data-stu-id="2e476-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="2e476-123"><xref:System.Windows.Controls.TextBlock> Отображает значение «Медленнее значение».</span><span class="sxs-lookup"><span data-stu-id="2e476-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="2e476-124">По прошествии 5 секунд `SlowestDP` свойство возвращает значение «Медленных значение».</span><span class="sxs-lookup"><span data-stu-id="2e476-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="2e476-125">Эта привязка имеет самый высокий приоритет, так как она указывается в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="2e476-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="2e476-126"><xref:System.Windows.Controls.TextBlock> Теперь отображается значение «Медленных значение».</span><span class="sxs-lookup"><span data-stu-id="2e476-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="2e476-127">В разделе <xref:System.Windows.Data.PriorityBinding> сведения о того, что считается успешной возвращаемое значение из привязки.</span><span class="sxs-lookup"><span data-stu-id="2e476-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e476-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2e476-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2e476-129">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="2e476-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="2e476-130">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="2e476-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
