---
title: Практическое руководство. Обработка перенаправленных событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: 80b3be439498c0dc448322d1e7daf30202a470dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-a-routed-event"></a>Практическое руководство. Обработка перенаправленных событий
В этом примере показаны принципы работы восходящей маршрутизации событий и создания обработчика, который может обрабатывать данные перенаправленных событий.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементы упорядочены в структуру типа "дерево элементов". Родительский элемент может участвовать в обработке событий, которые изначально вызываются его дочерними элементами в дереве элементов. Это становится возможным из-за маршрутизации событий.  
  
 Перенаправленные события обычно обрабатываются с использованием одной из двух стратегий маршрутизации: восходящей или нисходящей. В этом примере основное внимание уделяется восходящей событий и использует <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> событие, чтобы показать, как работает маршрутизация.  
  
 В следующем примере создается два <xref:System.Windows.Controls.Button> определяет и использует [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] атрибут синтаксис, чтобы присоединить обработчик событий общий родительский элемент, который в данном примере — <xref:System.Windows.Controls.StackPanel>. Вместо присоединения отдельных обработчиков событий для каждого <xref:System.Windows.Controls.Button> дочерний элемент, в примере используется синтаксис атрибутов для присоединения обработчика событий <xref:System.Windows.Controls.StackPanel> родительского элемента. Этот шаблон обработки событий показывает, как использовать маршрутизацию событий в качестве техники для уменьшения количества элементов, к которым прикреплен обработчик. Все события восходящей для каждого <xref:System.Windows.Controls.Button> маршрут через родительский элемент.  
  
 Обратите внимание, что на родительском <xref:System.Windows.Controls.StackPanel> элемент, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> имя события, указанный как атрибут частично определяется путем именования <xref:System.Windows.Controls.Button> класса. <xref:System.Windows.Controls.Button> Класс <xref:System.Windows.Controls.Primitives.ButtonBase> производным классом, имеющим <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий в своем списке членов. Необходимо использовать этот метод частичного определения для прикрепления обработчика событий, если обрабатываемое событие не существует в списке участников элемента, к которому прикреплен обработчик перенаправленного события.  
  
 [!code-xaml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 В следующем примере показана обработка <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий.  В этом примере сообщается, какой элемент обрабатывает событие, а какой — вызывает. Обработчик событий выполняется, когда пользователь нажимает одну из кнопок.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.RoutedEvent>  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)  
 [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
