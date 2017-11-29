---
title: "Практическое руководство. Создание пользовательских перенаправленных событий"
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
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e901242b265e0012f9ad65d9eaab89b1b63b40ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-routed-event"></a>Практическое руководство. Создание пользовательских перенаправленных событий
Для поддержки маршрутизации события в пользовательском событии, необходимо зарегистрировать <xref:System.Windows.RoutedEvent> с помощью <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> метод. В этом примере демонстрируются основные принципы создания пользовательских перенаправленных событий.  
  
## <a name="example"></a>Пример  
 Как показано в следующем примере, нужно сначала зарегистрировать <xref:System.Windows.RoutedEvent> с помощью <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> метод. По соглашению <xref:System.Windows.RoutedEvent> имя статического поля должно заканчиваться суффиксом ***событие***. В этом примере событие называется `Tap` и стратегия маршрутизации события – <xref:System.Windows.RoutingStrategy.Bubble>. После вызова регистрации можно предоставить для этого события методы доступа к событию добавления и удаления [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  
  
 Обратите внимание, что несмотря на то что в этом примере событие вызывается виртуальным методом `OnTap`, метод вызова события и его реагирование на изменения зависят от ваших потребностей.  
  
 Обратите внимание, что в этом примере в основном реализуется весь подкласс <xref:System.Windows.Controls.Button>; Этот подкласс создается в виде отдельной сборки и затем создан в качестве пользовательского класса на отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы. Это призвано проиллюстрировать тот факт, что производные от классов элементы управления можно вставлять в деревья, состоящие из других элементов управления, и что в этой ситуации пользовательские события в этих элементах управления имеют те же функции маршрутизации событий, что и собственный элемент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Туннельный события создаются таким же способом, но с <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> значение <xref:System.Windows.RoutingStrategy.Tunnel> в вызове регистрации. По соглашению события нисходящей маршрутизации в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют префикс Preview.  
  
 Пример функционирования восходящей маршрутизации событий см. в разделе [Обработка перенаправленных событий](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
