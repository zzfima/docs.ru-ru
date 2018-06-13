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
ms.openlocfilehash: a8aa038008ed93cedfe49fde4e0269712b4fb19a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543710"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="6151b-102">Практическое руководство. Создание пользовательских перенаправленных событий</span><span class="sxs-lookup"><span data-stu-id="6151b-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="6151b-103">Для поддержки маршрутизации события в пользовательском событии, необходимо зарегистрировать <xref:System.Windows.RoutedEvent> с помощью <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6151b-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="6151b-104">В этом примере демонстрируются основные принципы создания пользовательских перенаправленных событий.</span><span class="sxs-lookup"><span data-stu-id="6151b-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6151b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6151b-105">Example</span></span>  
 <span data-ttu-id="6151b-106">Как показано в следующем примере, нужно сначала зарегистрировать <xref:System.Windows.RoutedEvent> с помощью <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6151b-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="6151b-107">По соглашению <xref:System.Windows.RoutedEvent> имя статического поля должно заканчиваться суффиксом ***событие***.</span><span class="sxs-lookup"><span data-stu-id="6151b-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="6151b-108">В этом примере событие называется `Tap` и стратегия маршрутизации события – <xref:System.Windows.RoutingStrategy.Bubble>.</span><span class="sxs-lookup"><span data-stu-id="6151b-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="6151b-109">После вызова регистрации можно предоставить для этого события методы доступа к событию добавления и удаления [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6151b-109">After the registration call, you can provide add-and-remove [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event accessors for the event.</span></span>  
  
 <span data-ttu-id="6151b-110">Обратите внимание, что несмотря на то что в этом примере событие вызывается виртуальным методом `OnTap`, метод вызова события и его реагирование на изменения зависят от ваших потребностей.</span><span class="sxs-lookup"><span data-stu-id="6151b-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="6151b-111">Обратите внимание, что в этом примере в основном реализуется весь подкласс <xref:System.Windows.Controls.Button>; Этот подкласс создается в виде отдельной сборки и затем создан в качестве пользовательского класса на отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="6151b-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="6151b-112">Это призвано проиллюстрировать тот факт, что производные от классов элементы управления можно вставлять в деревья, состоящие из других элементов управления, и что в этой ситуации пользовательские события в этих элементах управления имеют те же функции маршрутизации событий, что и собственный элемент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6151b-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="6151b-113">Туннельный события создаются таким же способом, но с <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> значение <xref:System.Windows.RoutingStrategy.Tunnel> в вызове регистрации.</span><span class="sxs-lookup"><span data-stu-id="6151b-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="6151b-114">По соглашению события нисходящей маршрутизации в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют префикс Preview.</span><span class="sxs-lookup"><span data-stu-id="6151b-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="6151b-115">Пример функционирования восходящей маршрутизации событий см. в разделе [Обработка перенаправленных событий](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).</span><span class="sxs-lookup"><span data-stu-id="6151b-115">To see an example of how bubbling events work, see [Handle a Routed Event](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6151b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6151b-116">See Also</span></span>  
 [<span data-ttu-id="6151b-117">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="6151b-117">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="6151b-118">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="6151b-118">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="6151b-119">Общие сведения о разработке элементов управления</span><span class="sxs-lookup"><span data-stu-id="6151b-119">Control Authoring Overview</span></span>](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
