---
title: Практическое руководство. Создание пользовательских перенаправленных событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401467"
---
# <a name="how-to-create-a-custom-routed-event"></a>Практическое руководство. Создание пользовательских перенаправленных событий
Чтобы пользовательское событие поддерживало маршрутизацию событий, необходимо зарегистрировать объект <xref:System.Windows.RoutedEvent> <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> с помощью метода. В этом примере демонстрируются основные принципы создания пользовательских перенаправленных событий.  
  
## <a name="example"></a>Пример  
 Как показано в следующем примере, сначала регистрируется <xref:System.Windows.RoutedEvent> <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> с помощью метода. По соглашению <xref:System.Windows.RoutedEvent> имя статического поля должно заканчиваться ***событием***суффикса. В этом примере имя события равно `Tap` , а стратегия маршрутизации события —. <xref:System.Windows.RoutingStrategy.Bubble> После вызова регистрации можно предоставить методы доступа к событиям Add-and-Remove среды CLR для события.  
  
 Обратите внимание, что несмотря на то что в этом примере событие вызывается виртуальным методом `OnTap`, метод вызова события и его реагирование на изменения зависят от ваших потребностей.  
  
 Обратите внимание, что в этом примере реализуется целый <xref:System.Windows.Controls.Button>подкласс класса; этот подкласс создается как отдельная сборка, а затем создается на отдельной [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] странице в качестве пользовательского класса. Это призвано проиллюстрировать тот факт, что производные от классов элементы управления можно вставлять в деревья, состоящие из других элементов управления, и что в этой ситуации пользовательские события в этих элементах управления имеют те же функции маршрутизации событий, что и собственный элемент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 События туннелирования создаются таким же образом, но с <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> <xref:System.Windows.RoutingStrategy.Tunnel> параметром в вызове регистрации. По соглашению события нисходящей маршрутизации в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют префикс Preview.  
  
 Пример функционирования восходящей маршрутизации событий см. в разделе [Обработка перенаправленных событий](how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
- [Общие сведения о входных данных](input-overview.md)
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
