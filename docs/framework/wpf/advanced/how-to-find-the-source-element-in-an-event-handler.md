---
title: "Практическое руководство. Поиск элемента источника в обработчике событий"
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
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e9746683ec5b7ad142591c2b419f9af21be8d69c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="f268f-102">Практическое руководство. Поиск элемента источника в обработчике событий</span><span class="sxs-lookup"><span data-stu-id="f268f-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="f268f-103">В этом примере показано, как найти элемент источника в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="f268f-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f268f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f268f-104">Example</span></span>  
 <span data-ttu-id="f268f-105">В следующем примере показан <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчика событий, объявленных в файле кода.</span><span class="sxs-lookup"><span data-stu-id="f268f-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="f268f-106">Когда пользователь нажимает кнопку обработчик, к которому присоединена, обработчик изменяет значение свойства.</span><span class="sxs-lookup"><span data-stu-id="f268f-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="f268f-107">В коде обработчика используется <xref:System.Windows.RoutedEventArgs.Source%2A> данные о событии, отчет в аргументах события, чтобы изменить свойство <xref:System.Windows.FrameworkElement.Width%2A> значения свойства в <xref:System.Windows.RoutedEventArgs.Source%2A> элемент.</span><span class="sxs-lookup"><span data-stu-id="f268f-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="f268f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f268f-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="f268f-109">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="f268f-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="f268f-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f268f-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
