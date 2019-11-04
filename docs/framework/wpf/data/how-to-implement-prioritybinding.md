---
title: Практическое руководство. Реализация класса PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459782"
---
# <a name="how-to-implement-prioritybinding"></a>Практическое руководство. Реализация класса PriorityBinding
<xref:System.Windows.Data.PriorityBinding> в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] работает путем указания списка привязок. Список привязок упорядочивается от наивысшего приоритета к низшему приоритету. Если привязка с наивысшим приоритетом возвращает значение успешно при обработке, то нет необходимости обрабатывать другие привязки в списке. Может быть, если привязка с наивысшим приоритетом занимает много времени, поэтому следующий высший приоритет, возвращающий значение, будет использоваться до тех пор, пока привязка с более высоким приоритетом не вернет значение.  
  
## <a name="example"></a>Пример  
 Чтобы продемонстрировать, как работает <xref:System.Windows.Data.PriorityBinding>, объект `AsyncDataSource` был создан со следующими тремя свойствами: `FastDP`, `SlowerDP`и `SlowestDP`.  
  
 Метод доступа Get `FastDP` возвращает значение элемента данных `_fastDP`.  
  
 Метод доступа Get `SlowerDP` ожидает 3 секунды перед возвратом значения элемента данных `_slowerDP`.  
  
 Метод доступа Get `SlowestDP` ожидает 5 секунд перед возвратом значения элемента данных `_slowestDP`.  
  
> [!NOTE]
> Этот пример приведен только в качестве демонстрации. Рекомендации по .NET рекомендуются для определения свойств, порядок которых меньше, чем набор полей. Дополнительные сведения см. в разделе [Выбор между свойствами и методами](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Свойство <xref:System.Windows.Controls.TextBlock.Text%2A> привязывается к приведенной выше `AsyncDS` с помощью <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Когда обработчик привязки обрабатывает <xref:System.Windows.Data.Binding> объекты, он начинается с первого <xref:System.Windows.Data.Binding>, который привязан к свойству `SlowestDP`. При обработке этого <xref:System.Windows.Data.Binding> значение не возвращается, так как оно находится в спящем режиме в течение 5 секунд, поэтому обрабатывается следующий элемент <xref:System.Windows.Data.Binding>. Следующая <xref:System.Windows.Data.Binding> не возвращает значение, так как оно находится в спящем режиме в течение 3 секунд. Затем подсистема привязки переместится на следующий элемент <xref:System.Windows.Data.Binding>, который привязан к свойству `FastDP`. Этот <xref:System.Windows.Data.Binding> возвращает значение "быстрое значение". В <xref:System.Windows.Controls.TextBlock> теперь отображается значение "быстрое значение".  
  
 По истечении 3 секунды свойство `SlowerDP` возвращает значение "медленное значение". Затем <xref:System.Windows.Controls.TextBlock> выводит значение "медленное значение".  
  
 По истечении 5 секунд свойство `SlowestDP` возвращает значение "самое медленное значение". Эта привязка имеет наивысший приоритет, так как она указана первым. В <xref:System.Windows.Controls.TextBlock> теперь отображается значение "самое медленное значение".  
  
 Сведения о том, что считается успешным возвращаемым значением из привязки, см. в разделе <xref:System.Windows.Data.PriorityBinding>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
