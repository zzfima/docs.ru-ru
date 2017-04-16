---
title: "Практическое руководство. Поиск элемента источника в обработчике событий | Microsoft Docs"
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
  - "обработчики событий, поиск исходного элемента в"
  - "исходный элемент в обработчиках событий"
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Поиск элемента источника в обработчике событий
В этом примере показано, как найти элемент источника в обработчике событий.  
  
## Пример  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, объявленный в файле кода программной части.  Когда пользователь нажимает кнопку, за которой закреплен обработчик, обработчик изменяет значение свойства.  В коде обработчика используется свойство <xref:System.Windows.RoutedEventArgs.Source%2A> данных перенаправленного события, сообщающее в аргументах события о необходимости изменения значения свойства <xref:System.Windows.FrameworkElement.Width%2A> в элементе <xref:System.Windows.RoutedEventArgs.Source%2A>.  
  
 [!code-xml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## См. также  
 <xref:System.Windows.RoutedEventArgs>   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)