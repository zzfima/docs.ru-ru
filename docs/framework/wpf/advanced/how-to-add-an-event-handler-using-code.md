---
title: "Практическое руководство. Добавление обработчика событий с помощью кода"
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
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3abcd441219e58df2e5a0d4b66447e255c6aabd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="9e45d-102">Практическое руководство. Добавление обработчика событий с помощью кода</span><span class="sxs-lookup"><span data-stu-id="9e45d-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="9e45d-103">В этом примере показано, как добавить обработчик событий к элементу с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="9e45d-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="9e45d-104">Если вы хотите добавить обработчик событий для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элемента и разметка страницы, которая содержит элемент, уже загружена, необходимо добавить обработчик, с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="9e45d-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="9e45d-105">Кроме того Если вы создаете вверх по дереву элементов для приложения, используя только код и не объявляет никаких элементов, используя [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно вызвать специальные методы для добавления обработчиков событий в построенное дерево элементов.</span><span class="sxs-lookup"><span data-stu-id="9e45d-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e45d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="9e45d-106">Example</span></span>  
 <span data-ttu-id="9e45d-107">В следующем примере добавляется новый <xref:System.Windows.Controls.Button> существующей страницы, которая изначально определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e45d-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="9e45d-108">Файл кода реализует метод обработчика событий и добавляет этот метод как новый обработчик событий на <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9e45d-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="9e45d-109">[!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] Примере `+=` оператор, чтобы назначить обработчик события.</span><span class="sxs-lookup"><span data-stu-id="9e45d-109">The [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="9e45d-110">Это тот же оператор, используемый для назначения обработчика в [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] модели обработки событий.</span><span class="sxs-lookup"><span data-stu-id="9e45d-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]<span data-ttu-id="9e45d-111">не поддерживает этот оператор как средство для добавления обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="9e45d-111"> does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="9e45d-112">Вместо этого требуется один из двух способов:</span><span class="sxs-lookup"><span data-stu-id="9e45d-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="9e45d-113">Используйте <xref:System.Windows.UIElement.AddHandler%2A> метод совместно с `AddressOf` оператор для ссылки на реализацию обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9e45d-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="9e45d-114">Используйте `Handles` ключевое слово в качестве части определения обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9e45d-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="9e45d-115">Этот метод не показан здесь; в разделе [Visual Basic и обработка событий WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="9e45d-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="9e45d-116">Добавление обработчика событий в изначально разобранную [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы намного проще.</span><span class="sxs-lookup"><span data-stu-id="9e45d-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="9e45d-117">В элементе объекта, где требуется добавить обработчик событий добавьте атрибут, который совпадает с именем события, которое необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="9e45d-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="9e45d-118">Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенные в файле кода программной части [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="9e45d-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="9e45d-119">Дополнительные сведения см. в разделе [Обзор XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) или [направлено Общие сведения о событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9e45d-119">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) or [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e45d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9e45d-120">See Also</span></span>  
 [<span data-ttu-id="9e45d-121">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="9e45d-121">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="9e45d-122">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="9e45d-122">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
