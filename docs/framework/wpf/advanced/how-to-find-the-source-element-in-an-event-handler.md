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
ms.openlocfilehash: c3ae893cd7fd7780854d6eb6ffd682feadb5c5a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="58395-102">Практическое руководство. Поиск элемента источника в обработчике событий</span><span class="sxs-lookup"><span data-stu-id="58395-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="58395-103">В этом примере показано, как найти элемент источника в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="58395-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58395-104">Пример</span><span class="sxs-lookup"><span data-stu-id="58395-104">Example</span></span>  
 <span data-ttu-id="58395-105">В следующем примере показан <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчика событий, объявленных в файле кода.</span><span class="sxs-lookup"><span data-stu-id="58395-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="58395-106">Когда пользователь нажимает кнопку обработчик, к которому присоединена, обработчик изменяет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="58395-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="58395-107">В коде обработчика используется <xref:System.Windows.RoutedEventArgs.Source%2A> данные о событии, отчет в аргументах события, чтобы изменить свойство <xref:System.Windows.FrameworkElement.Width%2A> значения свойства в <xref:System.Windows.RoutedEventArgs.Source%2A> элемент.</span><span class="sxs-lookup"><span data-stu-id="58395-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="58395-108">См. также</span><span class="sxs-lookup"><span data-stu-id="58395-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="58395-109">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="58395-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="58395-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="58395-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
