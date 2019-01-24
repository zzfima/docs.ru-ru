---
title: Как выполнить Поиск элемента источника в обработчике событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 4cdf1434f2d341cbc1e65541fd02ab4b5cad194d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536741"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="bc9cd-102">Как выполнить Поиск элемента источника в обработчике событий</span><span class="sxs-lookup"><span data-stu-id="bc9cd-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="bc9cd-103">В этом примере показано, как поиск элемента источника в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9cd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bc9cd-104">Example</span></span>  
 <span data-ttu-id="bc9cd-105">В следующем примере показан <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий, который объявлен в файле кода.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="bc9cd-106">Когда пользователь щелкает кнопку, чтобы присоединен обработчик, обработчик изменяет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="bc9cd-107">В коде обработчика используется <xref:System.Windows.RoutedEventArgs.Source%2A> свойство, указанное в отчетах в аргументах событий для изменения данных перенаправленное событие <xref:System.Windows.FrameworkElement.Width%2A> значение свойства на <xref:System.Windows.RoutedEventArgs.Source%2A> элемент.</span><span class="sxs-lookup"><span data-stu-id="bc9cd-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="bc9cd-108">См. также</span><span class="sxs-lookup"><span data-stu-id="bc9cd-108">See also</span></span>
- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="bc9cd-109">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="bc9cd-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [<span data-ttu-id="bc9cd-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="bc9cd-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
