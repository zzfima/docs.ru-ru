---
title: Практическое руководство. Реализация класса PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: cf0ed5c2b55358d3a583ac89e307b23b3ab08a9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-prioritybinding"></a>Практическое руководство. Реализация класса PriorityBinding
<xref:System.Windows.Data.PriorityBinding> в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] работает путем указания списка привязок. Список привязок упорядочен от наивысшего приоритета к более низкому приоритету. Если привязка наивысшего приоритета возвращает значение успешно при его обработке то нет необходимости обрабатывать другие привязки в списке. Он может случиться, что привязка наивысшего приоритета занимает много времени для оценки, будет использоваться следующий высокий приоритет, успешно возвращает значение, до привязки с более высоким приоритетом успешно возвращает значение.  
  
## <a name="example"></a>Пример  
 Чтобы продемонстрировать, как <xref:System.Windows.Data.PriorityBinding> работает, `AsyncDataSource` объект был создан со следующими тремя свойствами: `FastDP`, `SlowerDP`, и `SlowestDP`.  
  
 Метод доступа get `FastDP` возвращает значение `_fastDP` члена данных.  
  
 Метод доступа get `SlowerDP` ожидает в течение 3 секунд перед возвратом значения `_slowerDP` элемента данных.  
  
 Метод доступа get `SlowestDP` ожидает 5 секунд перед возвратом значения `_slowestDP` элемента данных.  
  
> [!NOTE]
>  Этот пример приведен только в качестве демонстрации. [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Правила рекомендованы для определения свойств, которые являются порядков медленнее, чем мог бы быть набор полей. Дополнительные сведения см. в разделе [NIB: Выбор между свойствами и методами](http://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A> Связывается в указанное свойство `AsyncDS` с помощью <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Когда обработчик привязки обрабатывает <xref:System.Windows.Data.Binding> объектов, он начинает с первой <xref:System.Windows.Data.Binding>, который привязан к `SlowestDP` свойство. Если это <xref:System.Windows.Data.Binding> — обработки, она не успешного возвращения значения, так как он находится в спящем режиме для 5 секунд, поэтому следующего <xref:System.Windows.Data.Binding> обработки элемента. Следующий <xref:System.Windows.Data.Binding> не успешного возвращения значения, так как он находится в спящем режиме в течение 3 секунд. Затем обработчик привязки перемещается к следующему <xref:System.Windows.Data.Binding> элемент, который привязан к `FastDP` свойство. Это <xref:System.Windows.Data.Binding> возвращает значение «Fast Value». <xref:System.Windows.Controls.TextBlock> Теперь отображается значение «Fast Value».  
  
 По прошествии 3 секунд `SlowerDP` свойство возвращает значение «Медленнее значение». <xref:System.Windows.Controls.TextBlock> Отображает значение «Медленнее значение».  
  
 По прошествии 5 секунд `SlowestDP` свойство возвращает значение «Медленных значение». Эта привязка имеет самый высокий приоритет, так как она указывается в первую очередь. <xref:System.Windows.Controls.TextBlock> Теперь отображается значение «Медленных значение».  
  
 В разделе <xref:System.Windows.Data.PriorityBinding> сведения о того, что считается успешной возвращаемое значение из привязки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
