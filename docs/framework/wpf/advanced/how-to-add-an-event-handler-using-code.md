---
title: "Практическое руководство. Добавление обработчика событий с помощью кода | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "обработчики событий, добавление"
  - "XAML, добавление обработчиков событий"
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Добавление обработчика событий с помощью кода
В этом примере демонстрируется добавление обработчика событий к элементу с помощью кода.  
  
 Если вам необходимо добавить обработчик событий к элементу [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а разметка страницы, которая содержит элемент, уже загружена, вам необходимо добавлять обработчик с помощью кода.  Кроме того, если вы строите дерево элементов для приложения, используя только код, и не объявляете никаких элементов, используя [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], вы можете вызвать специальные методы для добавления обработчиков событий в построенное дерево элементов.  
  
## Пример  
 В следующем примере добавляется новый <xref:System.Windows.Controls.Button> на существующую страницу, которая первоначально определяется в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Файл кода программной части реализует метод обработчика событий и добавляет этот метод в качестве нового обработчика событий в <xref:System.Windows.Controls.Button>.  
  
 В примере [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] используется оператор `+=` для присвоения обработчика событию.  Это тот же оператор, что используется для назначения обработчика в модели обработки событий [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] не поддерживает этот оператор для добавления обработчиков событий.  Вместо этого требуется один из двух методов:  
  
-   Использовать метод <xref:System.Windows.UIElement.AddHandler%2A>, вместе с оператором `AddressOf`, для ссылки на реализацию обработчика событий.  
  
-   Использовать ключевое слово `Handles` в качестве части определения обработчика событий.  Этот метод не показан здесь; см. [Обработка событий в Visual Basic и WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Добавление обработчика событий в изначально разобранную страницу [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] намного проще.  В элемент объекта, в который требуется добавить обработчик событий, добавьте атрибут, который совпадает с именем события, которое вам требуется обработать.  Затем укажите значение этого атрибута в качестве имени метода обработчика событий, который вы определили в файле кода программной части страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Дополнительные сведения см. в разделе [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) или [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## См. также  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)