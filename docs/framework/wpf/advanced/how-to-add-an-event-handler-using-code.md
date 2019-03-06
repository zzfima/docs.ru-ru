---
title: Практическое руководство. Добавление обработчика событий с помощью кода
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 05eaae0f5b893f42d421717ac73373d4c79004c4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352195"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="41d51-102">Практическое руководство. Добавление обработчика событий с помощью кода</span><span class="sxs-lookup"><span data-stu-id="41d51-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="41d51-103">В этом примере показано, как добавить обработчик событий к элементу с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="41d51-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="41d51-104">Если вы хотите добавить обработчик событий к [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элемент и разметка страницы, которая содержит элемент уже был загружен, необходимо добавить обработчик с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="41d51-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="41d51-105">Кроме того Если вы создаете вверх по дереву элементов, для приложения, используя только код и не объявляет никаких элементов, используя [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно вызывать методы, определенные для добавления обработчиков событий в построенное дерево элементов.</span><span class="sxs-lookup"><span data-stu-id="41d51-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41d51-106">Пример</span><span class="sxs-lookup"><span data-stu-id="41d51-106">Example</span></span>  
 <span data-ttu-id="41d51-107">В следующем примере добавляется новый <xref:System.Windows.Controls.Button> на существующую страницу, которая изначально определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41d51-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="41d51-108">Файл с выделенным кодом реализует метод обработчика событий и добавляет этот метод как новый обработчик событий на <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="41d51-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="41d51-109">C# Примере `+=` оператор присвоения обработчика события.</span><span class="sxs-lookup"><span data-stu-id="41d51-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="41d51-110">Это тот же оператор, который используется для назначения обработчика в [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] модели обработки событий.</span><span class="sxs-lookup"><span data-stu-id="41d51-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="41d51-111">Microsoft Visual Basic не поддерживает этот оператор как средства для добавления обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="41d51-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="41d51-112">Вместо этого требуется один из двух способов:</span><span class="sxs-lookup"><span data-stu-id="41d51-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="41d51-113">Используйте <xref:System.Windows.UIElement.AddHandler%2A> метод совместно с `AddressOf` оператор, для ссылки на реализацию обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="41d51-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="41d51-114">Используйте `Handles` ключевое слово как часть определения обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="41d51-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="41d51-115">Этот способ не показан здесь. см. в разделе [Visual Basic и обработка событий WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="41d51-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="41d51-116">Добавление обработчика событий в изначально разобранную [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы намного проще.</span><span class="sxs-lookup"><span data-stu-id="41d51-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="41d51-117">В элементе объекта, где вы хотите добавить обработчик событий добавьте атрибут, который совпадает с именем события, которое необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="41d51-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="41d51-118">Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенные в файле кода программной [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="41d51-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="41d51-119">Дополнительные сведения см. в разделе [Обзор XAML (WPF)](xaml-overview-wpf.md) или [Routed Events Overview](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="41d51-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d51-120">См. также</span><span class="sxs-lookup"><span data-stu-id="41d51-120">See also</span></span>
- [<span data-ttu-id="41d51-121">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="41d51-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="41d51-122">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="41d51-122">How-to Topics</span></span>](events-how-to-topics.md)
