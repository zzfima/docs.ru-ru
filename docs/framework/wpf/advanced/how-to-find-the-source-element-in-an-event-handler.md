---
title: Практическое руководство. Поиск элемента источника в обработчике событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 8c1ff53e5af1ddfda17328291c5e22b57a8fe0e2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359475"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="cf124-102">Практическое руководство. Поиск элемента источника в обработчике событий</span><span class="sxs-lookup"><span data-stu-id="cf124-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="cf124-103">В этом примере показано, как поиск элемента источника в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="cf124-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf124-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cf124-104">Example</span></span>  
 <span data-ttu-id="cf124-105">В следующем примере показан <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий, который объявлен в файле кода.</span><span class="sxs-lookup"><span data-stu-id="cf124-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="cf124-106">Когда пользователь щелкает кнопку, чтобы присоединен обработчик, обработчик изменяет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="cf124-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="cf124-107">В коде обработчика используется <xref:System.Windows.RoutedEventArgs.Source%2A> свойство, указанное в отчетах в аргументах событий для изменения данных перенаправленное событие <xref:System.Windows.FrameworkElement.Width%2A> значение свойства на <xref:System.Windows.RoutedEventArgs.Source%2A> элемент.</span><span class="sxs-lookup"><span data-stu-id="cf124-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="cf124-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cf124-108">See also</span></span>
- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="cf124-109">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="cf124-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="cf124-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="cf124-110">How-to Topics</span></span>](events-how-to-topics.md)
