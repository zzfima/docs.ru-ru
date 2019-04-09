---
title: Практическое руководство. Создание пользовательских перенаправленных событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: a3850875c8ca747f8709b55f8fe721d25be24304
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091477"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="e9320-102">Практическое руководство. Создание пользовательских перенаправленных событий</span><span class="sxs-lookup"><span data-stu-id="e9320-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="e9320-103">Пользовательское событие поддерживало маршрутизацию событий, необходимо зарегистрировать <xref:System.Windows.RoutedEvent> с помощью <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e9320-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="e9320-104">В этом примере демонстрируются основные принципы создания пользовательских перенаправленных событий.</span><span class="sxs-lookup"><span data-stu-id="e9320-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9320-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e9320-105">Example</span></span>  
 <span data-ttu-id="e9320-106">Как показано в следующем примере сначала зарегистрировать <xref:System.Windows.RoutedEvent> с помощью <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e9320-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="e9320-107">По соглашению <xref:System.Windows.RoutedEvent> имя статического поля должно заканчиваться суффиксом ***событий***.</span><span class="sxs-lookup"><span data-stu-id="e9320-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="e9320-108">В этом примере событие называется `Tap` и стратегия маршрутизации события – <xref:System.Windows.RoutingStrategy.Bubble>.</span><span class="sxs-lookup"><span data-stu-id="e9320-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="e9320-109">После вызова регистрации можно предоставить для этого события методы доступа к событию добавления и удаления [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9320-109">After the registration call, you can provide add-and-remove [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event accessors for the event.</span></span>  
  
 <span data-ttu-id="e9320-110">Обратите внимание, что несмотря на то что в этом примере событие вызывается виртуальным методом `OnTap`, метод вызова события и его реагирование на изменения зависят от ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="e9320-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="e9320-111">Обратите внимание, что по сути, в этом примере реализуется весь подкласс <xref:System.Windows.Controls.Button>; Этот подкласс создается в виде отдельной сборки, а затем создается экземпляр в виде пользовательского класса на отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="e9320-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="e9320-112">Это призвано проиллюстрировать тот факт, что производные от классов элементы управления можно вставлять в деревья, состоящие из других элементов управления, и что в этой ситуации пользовательские события в этих элементах управления имеют те же функции маршрутизации событий, что и собственный элемент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9320-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="e9320-113">События нисходящей маршрутизации создаются таким же способом, но с <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> присвоено <xref:System.Windows.RoutingStrategy.Tunnel> в вызове регистрации.</span><span class="sxs-lookup"><span data-stu-id="e9320-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="e9320-114">По соглашению события нисходящей маршрутизации в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют префикс Preview.</span><span class="sxs-lookup"><span data-stu-id="e9320-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="e9320-115">Пример функционирования восходящей маршрутизации событий см. в разделе [Обработка перенаправленных событий](how-to-handle-a-routed-event.md).</span><span class="sxs-lookup"><span data-stu-id="e9320-115">To see an example of how bubbling events work, see [Handle a Routed Event](how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9320-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e9320-116">See also</span></span>

- [<span data-ttu-id="e9320-117">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="e9320-117">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="e9320-118">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="e9320-118">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="e9320-119">Общие сведения о разработке элементов управления</span><span class="sxs-lookup"><span data-stu-id="e9320-119">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
