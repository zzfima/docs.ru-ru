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
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Практическое руководство. Поиск элемента источника в обработчике событий
В этом примере показано, как найти элемент источника в обработчике событий.  
  
## <a name="example"></a>Пример  
 В следующем примере показан <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчика событий, объявленных в файле кода. Когда пользователь нажимает кнопку обработчик, к которому присоединена, обработчик изменяет значение свойства. В коде обработчика используется <xref:System.Windows.RoutedEventArgs.Source%2A> данные о событии, отчет в аргументах события, чтобы изменить свойство <xref:System.Windows.FrameworkElement.Width%2A> значения свойства в <xref:System.Windows.RoutedEventArgs.Source%2A> элемент.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.RoutedEventArgs>  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
