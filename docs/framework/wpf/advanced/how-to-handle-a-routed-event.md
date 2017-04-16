---
title: "Практическое руководство. Обработка перенаправленных событий | Microsoft Docs"
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
  - "WPF"
  - "перенаправляемые события, обработка"
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Практическое руководство. Обработка перенаправленных событий
В этом примере описаны принципы действия [всплывающих](GTMT) событий и способы написания обработчика, который может обрабатывать данные [перенаправленных событий](GTMT).  
  
## Пример  
 В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементы располагаются в структуре [дерева элементов](GTMT).  Родительский элемент может участвовать в обработке событий, которые изначально вызываются его дочерними элементами в дереве элементов.  Это возможно благодаря [маршрутизации событий](GTMT).  
  
 Перенаправленные события обычно следуют по одному из двух вариантов маршрутизации: [восходящей](GTMT) или [нисходящей](GTMT).  В этом примере основное внимание уделяется [всплывающему](GTMT) событию и используется событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=fullName>, чтобы показать, как работает маршрутизация.  
  
 В следующем примере создаются два элемента управления <xref:System.Windows.Controls.Button> и используется синтаксис атрибутов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для присоединения обработчика событий к общему родительскому элементу, которым в этом примере является элемент управления <xref:System.Windows.Controls.StackPanel>.  Вместо присоединения отдельных обработчиков событий для каждого дочернего элемента <xref:System.Windows.Controls.Button>, в примере используется синтаксис атрибута для присоединения обработчика событий к родительскому элементу <xref:System.Windows.Controls.StackPanel>.  Этот шаблон обработки событий показывает, как использовать маршрутизирование событий для снижения числа элементов, к которым присоединен обработчик.  Все [всплывающие](GTMT) события для каждого маршрута <xref:System.Windows.Controls.Button> направляются через родительский элемент.  
  
 Обратите внимание, что на родительском элементе <xref:System.Windows.Controls.StackPanel> имя события <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, указанное в качестве атрибута, частично определяется с помощью указания класса <xref:System.Windows.Controls.Button>.  Класс <xref:System.Windows.Controls.Button> является производным от класса <xref:System.Windows.Controls.Primitives.ButtonBase>, который содержит событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в своем списке членов.  Этот метод частичного уточнения для присоединения обработчика событий необходим, если обрабатываемое событие не существует в списке членов элемента, к которому присоединен обработчик перенаправленных событий.  
  
 [!code-xml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 В следующем примере показана обработка события <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  В примере сообщается, какой элемент обрабатывает событие и какой элемент вызывает событие.  Обработчик событий выполняется, когда пользователь нажимает одну из кнопок.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## См. также  
 <xref:System.Windows.RoutedEvent>   
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)   
 [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)