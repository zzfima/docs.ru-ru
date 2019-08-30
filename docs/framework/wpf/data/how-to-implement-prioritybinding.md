---
title: Практическое руководство. Реализация PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 4be1ce434eb1e169e8a19b56c92ca1efb48773d2
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169088"
---
# <a name="how-to-implement-prioritybinding"></a>Практическое руководство. Реализация PriorityBinding
<xref:System.Windows.Data.PriorityBinding>в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Works, указав список привязок. Список привязок упорядочивается от наивысшего приоритета к низшему приоритету. Если привязка с наивысшим приоритетом возвращает значение успешно при обработке, то нет необходимости обрабатывать другие привязки в списке. Может быть, если привязка с наивысшим приоритетом занимает много времени, поэтому следующий высший приоритет, возвращающий значение, будет использоваться до тех пор, пока привязка с более высоким приоритетом не вернет значение.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Data.PriorityBinding> Чтобы продемонстрировать `FastDP` `SlowerDP` `SlowestDP`, как работает, объектбылсоздансоследующимитремясвойствами:,и.`AsyncDataSource`  
  
 Метод доступа `FastDP` Get возвращает значение `_fastDP` элемента данных.  
  
 Метод доступа `SlowerDP` get ожидает 3 секунды перед возвратом значения `_slowerDP` элемента данных.  
  
 Метод доступа `SlowestDP` get ожидает 5 секунд перед возвратом значения `_slowestDP` элемента данных.  
  
> [!NOTE]
> Этот пример приведен только в качестве демонстрации. Рекомендации по .NET рекомендуются для определения свойств, порядок которых меньше, чем набор полей. Дополнительные сведения см. в разделе [Выбор между свойствами и методами](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Свойство привязывается к приведенному `AsyncDS` выше с помощью <xref:System.Windows.Data.PriorityBinding>: <xref:System.Windows.Controls.TextBlock.Text%2A>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Когда обработчик привязки обрабатывает <xref:System.Windows.Data.Binding> объекты, он начинается с первого <xref:System.Windows.Data.Binding>, `SlowestDP` который привязан к свойству. При обработке <xref:System.Windows.Data.Binding> это значение не возвращается, так как оно находится в режиме ожидания в течение 5 секунд, поэтому обрабатывается следующий <xref:System.Windows.Data.Binding> элемент. Следующая <xref:System.Windows.Data.Binding> ошибка не возвращает значение, так как оно находится в спящем режиме в течение 3 секунд. Затем обработчик привязки переместится на следующий <xref:System.Windows.Data.Binding> элемент, который привязан `FastDP` к свойству. Это <xref:System.Windows.Data.Binding> возвращает значение "быстрое значение". <xref:System.Windows.Controls.TextBlock> Теперь отображается значение "быстрое значение".  
  
 По `SlowerDP` истечении 3 секунды свойство возвращает значение "медленное значение". <xref:System.Windows.Controls.TextBlock> Затем выводит значение «медленное значение».  
  
 По `SlowestDP` истечении 5 секунд свойство возвращает значение "самое медленное значение". Эта привязка имеет наивысший приоритет, так как она указана первым. <xref:System.Windows.Controls.TextBlock> Теперь отображается значение "самое медленное значение".  
  
 Сведения <xref:System.Windows.Data.PriorityBinding> о том, что считается успешным возвращаемым значением из привязки, см. в разделе.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
