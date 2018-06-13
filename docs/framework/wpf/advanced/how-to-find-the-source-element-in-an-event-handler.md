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
ms.locfileid: "33544008"
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
