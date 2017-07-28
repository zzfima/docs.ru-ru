---
title: "Практическое руководство. Создание пользовательских перенаправленных событий | Microsoft Docs"
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
  - "создание, перенаправляемые события"
  - "события, маршрутизация"
  - "перенаправляемые события, создание"
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Создание пользовательских перенаправленных событий
Чтобы обеспечить поддержку [перенаправления событий](GTMT) в пользовательском событии, зарегистрируйте объект <xref:System.Windows.RoutedEvent> с помощью метода <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>.  В этом примере описываются основные принципы создания пользовательских перенаправленных событий.  
  
## Пример  
 Как показано в следующем примере, сначала выполняется регистрация объекта <xref:System.Windows.RoutedEvent> с помощью метода <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>.  В соответствии с соглашением, имя статического поля <xref:System.Windows.RoutedEvent> должно заканчиваться суффиксом ***Event***.  В этом примере для события `Tap` используется стратегия перенаправления событий <xref:System.Windows.RoutingStrategy>.  После вызова регистрации для события можно предоставить методы доступа для добавления и удаления событий [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  
  
 Обратите внимание, что даже при вызове события с помощью виртуального метода `OnTap` вызов события и реакция события на изменения зависят от потребностей разработчика.  
  
 Обратите внимание, что в этом примере в основном реализуется весь подкласс <xref:System.Windows.Controls.Button>. Этот подкласс создается в виде отдельной сборки, после чего на отдельной странице [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] создается его экземпляр в качестве пользовательского класса.  Это позволяет проиллюстрировать возможность вставки производных элементов управления в деревья, состоящие из других элементов управления. В этом случае пользовательские события в этих элементах управления включают в себя те же функции перенаправления событий, что и любой собственный элемент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Если создается событие с нисходящей маршрутизацией, при вызове регистрации для свойства <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> устанавливается значение <xref:System.Windows.RoutingStrategy>.  В соответствии с соглашением, в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к событиям с нисходящей маршрутизацией добавляется префикс "Preview".  
  
 Пример использования событий с восходящей маршрутизацией см. в разделе [Обработка перенаправленных событий](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
## См. также  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md)