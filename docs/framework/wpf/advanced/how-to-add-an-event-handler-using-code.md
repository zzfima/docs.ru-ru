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
ms.openlocfilehash: 017b32dc07f62cc4553a84f7b91687fb34a53c65
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937476"
---
# <a name="how-to-add-an-event-handler-using-code"></a>Практическое руководство. Добавление обработчика событий с помощью кода
В этом примере показано, как добавить обработчик событий в элемент с помощью кода.  
  
 Если необходимо добавить обработчик событий к [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементу, а страница разметки, содержащая этот элемент, уже загружена, необходимо добавить обработчик с помощью кода. Кроме того, если вы создаете дерево элементов для приложения полностью с помощью кода и не объявляете какие бы то ни [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]было элементы с помощью, можно вызывать определенные методы для добавления обработчиков событий в сконструированное дерево элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере добавляется новый <xref:System.Windows.Controls.Button> объект в существующую страницу, которая изначально определена [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]в. Файл кода программной части реализует метод обработчика событий, а затем добавляет этот метод в качестве нового обработчика <xref:System.Windows.Controls.Button>событий в.  
  
 В C# примере `+=` оператор используется для назначения обработчика для события. Это тот же оператор, который используется для назначения обработчика в модели обработки событий среды CLR. Microsoft Visual Basic не поддерживает этот оператор как средство добавления обработчиков событий. Вместо этого требуется один из двух методов:  
  
- Используйте метод вместе `AddressOf` с оператором для ссылки на реализацию обработчика событий. <xref:System.Windows.UIElement.AddHandler%2A>  
  
- `Handles` Используйте ключевое слово как часть определения обработчика событий. Этот метод не показан здесь; см. раздел [Обработка событий Visual Basic и WPF](visual-basic-and-wpf-event-handling.md).  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> Добавление обработчика событий на [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] странице изначально проанализировано гораздо проще. В элементе Object, куда нужно добавить обработчик событий, добавьте атрибут, соответствующий имени события, которое необходимо обменять. Затем укажите значение этого атрибута в качестве имени метода обработчика событий, определенного в файле кода программной части [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницы. Дополнительные сведения см. в разделе Общие сведения [о XAML (WPF)](xaml-overview-wpf.md) или перенаправленные [события](routed-events-overview.md).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
- [Разделы практического руководства](events-how-to-topics.md)
