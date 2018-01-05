---
title: "Практическое руководство. Обработка перенаправленных событий"
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
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c491ff4e231d932b3714d2d059b52bad2502368c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-a-routed-event"></a><span data-ttu-id="e19dd-102">Практическое руководство. Обработка перенаправленных событий</span><span class="sxs-lookup"><span data-stu-id="e19dd-102">How to: Handle a Routed Event</span></span>
<span data-ttu-id="e19dd-103">В этом примере показаны принципы работы восходящей маршрутизации событий и создания обработчика, который может обрабатывать данные перенаправленных событий.</span><span class="sxs-lookup"><span data-stu-id="e19dd-103">This example shows how bubbling events work and how to write a handler that can process the routed event data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e19dd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e19dd-104">Example</span></span>  
 <span data-ttu-id="e19dd-105">В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементы упорядочены в структуру типа "дерево элементов".</span><span class="sxs-lookup"><span data-stu-id="e19dd-105">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], elements are arranged in an element tree structure.</span></span> <span data-ttu-id="e19dd-106">Родительский элемент может участвовать в обработке событий, которые изначально вызываются его дочерними элементами в дереве элементов.</span><span class="sxs-lookup"><span data-stu-id="e19dd-106">The parent element can participate in the handling of events that are initially raised by child elements in the element tree.</span></span> <span data-ttu-id="e19dd-107">Это становится возможным из-за маршрутизации событий.</span><span class="sxs-lookup"><span data-stu-id="e19dd-107">This is possible because of event routing.</span></span>  
  
 <span data-ttu-id="e19dd-108">Перенаправленные события обычно обрабатываются с использованием одной из двух стратегий маршрутизации: восходящей или нисходящей.</span><span class="sxs-lookup"><span data-stu-id="e19dd-108">Routed events typically follow one of two routing strategies, bubbling or tunneling.</span></span> <span data-ttu-id="e19dd-109">В этом примере основное внимание уделяется восходящей событий и использует <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> событие, чтобы показать, как работает маршрутизация.</span><span class="sxs-lookup"><span data-stu-id="e19dd-109">This example focuses on the bubbling event and uses the <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> event to show how routing works.</span></span>  
  
 <span data-ttu-id="e19dd-110">В следующем примере создается два <xref:System.Windows.Controls.Button> определяет и использует [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибут синтаксис, чтобы присоединить обработчик событий общий родительский элемент, который в данном примере — <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="e19dd-110">The following example creates two <xref:System.Windows.Controls.Button> controls and uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax to attach an event handler to a common parent element, which in this example is <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="e19dd-111">Вместо присоединения отдельных обработчиков событий для каждого <xref:System.Windows.Controls.Button> дочерний элемент, в примере используется синтаксис атрибутов для присоединения обработчика событий <xref:System.Windows.Controls.StackPanel> родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="e19dd-111">Instead of attaching individual event handlers for each <xref:System.Windows.Controls.Button> child element, the example uses attribute syntax to attach the event handler to the <xref:System.Windows.Controls.StackPanel> parent element.</span></span> <span data-ttu-id="e19dd-112">Этот шаблон обработки событий показывает, как использовать маршрутизацию событий в качестве техники для уменьшения количества элементов, к которым прикреплен обработчик.</span><span class="sxs-lookup"><span data-stu-id="e19dd-112">This event-handling pattern shows how to use event routing as a technique for reducing the number of elements where a handler is attached.</span></span> <span data-ttu-id="e19dd-113">Все события восходящей для каждого <xref:System.Windows.Controls.Button> маршрут через родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="e19dd-113">All the bubbling events for each <xref:System.Windows.Controls.Button> route through the parent element.</span></span>  
  
 <span data-ttu-id="e19dd-114">Обратите внимание, что на родительском <xref:System.Windows.Controls.StackPanel> элемент, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> имя события, указанный как атрибут частично определяется путем именования <xref:System.Windows.Controls.Button> класса.</span><span class="sxs-lookup"><span data-stu-id="e19dd-114">Note that on the parent <xref:System.Windows.Controls.StackPanel> element, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event name specified as the attribute is partially qualified by naming the <xref:System.Windows.Controls.Button> class.</span></span> <span data-ttu-id="e19dd-115"><xref:System.Windows.Controls.Button> Класс <xref:System.Windows.Controls.Primitives.ButtonBase> производным классом, имеющим <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий в своем списке членов.</span><span class="sxs-lookup"><span data-stu-id="e19dd-115">The <xref:System.Windows.Controls.Button> class is a <xref:System.Windows.Controls.Primitives.ButtonBase> derived class that has the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in its members listing.</span></span> <span data-ttu-id="e19dd-116">Необходимо использовать этот метод частичного определения для прикрепления обработчика событий, если обрабатываемое событие не существует в списке участников элемента, к которому прикреплен обработчик перенаправленного события.</span><span class="sxs-lookup"><span data-stu-id="e19dd-116">This partial qualification technique for attaching an event handler is necessary if the event that is being handled does not exist in the members listing of the element where the routed event handler is attached.</span></span>  
  
 [!code-xaml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 <span data-ttu-id="e19dd-117">В следующем примере показана обработка <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="e19dd-117">The following example handles the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  <span data-ttu-id="e19dd-118">В этом примере сообщается, какой элемент обрабатывает событие, а какой — вызывает.</span><span class="sxs-lookup"><span data-stu-id="e19dd-118">The example reports which element handles the event and which element raises the event.</span></span> <span data-ttu-id="e19dd-119">Обработчик событий выполняется, когда пользователь нажимает одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="e19dd-119">The event handler is executed when the user clicks either button.</span></span>  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="e19dd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e19dd-120">See Also</span></span>  
 <xref:System.Windows.RoutedEvent>  
 [<span data-ttu-id="e19dd-121">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="e19dd-121">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="e19dd-122">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="e19dd-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="e19dd-123">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e19dd-123">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)  
 [<span data-ttu-id="e19dd-124">Подробное описание синтаксиса XAML</span><span class="sxs-lookup"><span data-stu-id="e19dd-124">XAML Syntax In Detail</span></span>](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
