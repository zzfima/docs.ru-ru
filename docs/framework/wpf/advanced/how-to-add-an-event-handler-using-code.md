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
# <a name="how-to-add-an-event-handler-using-code"></a>Практическое руководство. Добавление обработчика событий с помощью кода
В этом примере показано, как добавить обработчик событий к элементу с помощью кода.  
  
 Если вы хотите добавить обработчик событий для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элемента и разметка страницы, которая содержит элемент, уже загружена, необходимо добавить обработчик, с помощью кода. Кроме того Если вы создаете вверх по дереву элементов для приложения, используя только код и не объявляет никаких элементов, используя [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно вызвать специальные методы для добавления обработчиков событий в построенное дерево элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере добавляется новый <xref:System.Windows.Controls.Button> существующей страницы, которая изначально определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Файл кода реализует метод обработчика событий и добавляет этот метод как новый обработчик событий на <xref:System.Windows.Controls.Button>.  
  
 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] Примере `+=` оператор, чтобы назначить обработчик события. Это тот же оператор, используемый для назначения обработчика в [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] модели обработки событий. [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]не поддерживает этот оператор как средство для добавления обработчиков событий. Вместо этого требуется один из двух способов:  
  
-   Используйте <xref:System.Windows.UIElement.AddHandler%2A> метод совместно с `AddressOf` оператор для ссылки на реализацию обработчика событий.  
  
-   Используйте `Handles` ключевое слово в качестве части определения обработчика событий. Этот метод не показан здесь; в разделе [Visual Basic и обработка событий WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Добавление обработчика событий в изначально разобранную [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы намного проще. В элементе объекта, где требуется добавить обработчик событий добавьте атрибут, который совпадает с именем события, которое необходимо обработать. Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенные в файле кода программной части [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы. Дополнительные сведения см. в разделе [Обзор XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) или [направлено Общие сведения о событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
