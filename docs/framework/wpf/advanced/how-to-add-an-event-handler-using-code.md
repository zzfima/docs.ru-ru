---
title: Практическое руководство. Добавление обработчика событий с помощью кода
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460440"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Практическое руководство. Добавление обработчика событий с помощью кода
В этом примере показано, как добавить обработчик событий в элемент с помощью кода.  
  
 Если необходимо добавить обработчик событий к элементу [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а страница разметки, содержащая элемент, уже загружена, необходимо добавить обработчик с помощью кода. Кроме того, если вы создаете дерево элементов для приложения полностью с помощью кода и не объявляете какие либо элементы с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], вы можете вызывать определенные методы для добавления обработчиков событий в построенное дерево элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере добавляется новый <xref:System.Windows.Controls.Button> на существующую страницу, которая изначально определена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Файл кода программной части реализует метод обработчика событий, а затем добавляет этот метод в качестве нового обработчика событий в <xref:System.Windows.Controls.Button>.  
  
 В C# примере оператор `+=` используется для назначения обработчика для события. Это тот же оператор, который используется для назначения обработчика в модели обработки событий среды CLR. Microsoft Visual Basic не поддерживает этот оператор как средство добавления обработчиков событий. Вместо этого требуется один из двух методов:  
  
- Для ссылки на реализацию обработчика событий используйте метод <xref:System.Windows.UIElement.AddHandler%2A> вместе с оператором `AddressOf`.  
  
- Используйте ключевое слово `Handles` как часть определения обработчика событий. Этот метод не показан здесь; см. раздел [Обработка событий Visual Basic и WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Добавление обработчика событий на странице первоначального анализа [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] гораздо проще. В элементе Object, куда нужно добавить обработчик событий, добавьте атрибут, соответствующий имени события, которое необходимо обменять. Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенного в файле кода программной части страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Дополнительные сведения см. в разделе Общие сведения [о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) или [перенаправленные события](routed-events-overview.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
- [Разделы практического руководства](events-how-to-topics.md)
