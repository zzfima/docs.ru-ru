---
title: Практическое руководство. Реализация класса PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46490709"
---
# <a name="how-to-implement-prioritybinding"></a>Практическое руководство. Реализация класса PriorityBinding
<xref:System.Windows.Data.PriorityBinding> в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] работает путем указания списка привязок. Список привязок упорядочен от наиболее важных к наименее важным. Если привязка наивысшего приоритета возвращает значение успешно при его обработке то нет необходимости обрабатывать другие привязки в списке. Возможно, что привязка наивысшего приоритета занимает много времени для оценки, будет использоваться самым высоким приоритетом, которое возвращает значение успешно, пока не будет успешно возвращает значение привязки более высокий приоритет.  
  
## <a name="example"></a>Пример  
 Чтобы продемонстрировать, как <xref:System.Windows.Data.PriorityBinding> работает, `AsyncDataSource` объект создан со следующими тремя свойствами: `FastDP`, `SlowerDP`, и `SlowestDP`.  
  
 Метод доступа get `FastDP` возвращает значение `_fastDP` элемент данных.  
  
 Метод доступа get `SlowerDP` ожидает в течение 3 секунд перед возвратом значения `_slowerDP` элемента данных.  
  
 Метод доступа get `SlowestDP` ожидает в течение 5 секунд перед возвратом значения `_slowestDP` элемента данных.  
  
> [!NOTE]
>  Этот пример приведен только в качестве демонстрации. [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Правила рекомендованы для определения свойств, которые являются порядков медленнее, чем мог бы быть набор полей. Дополнительные сведения см. в разделе [NIB: Выбор между свойствами и методами](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A> Свойство привязывается к выше `AsyncDS` с помощью <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Когда обработчик привязки обрабатывает <xref:System.Windows.Data.Binding> объектов, он начинается с первого <xref:System.Windows.Data.Binding>, который привязан к `SlowestDP` свойство. Когда это <xref:System.Windows.Data.Binding> является обработки, он не возвращает значение успешно, так как он находится в спящем режиме на 5 секунд, поэтому следующий <xref:System.Windows.Data.Binding> обработки элемента. Следующий <xref:System.Windows.Data.Binding> не успешного возвращения значения, так как он находится в спящем режиме в течение 3 секунд. Затем обработчик привязки перемещается к следующему <xref:System.Windows.Data.Binding> элемент, который привязан к `FastDP` свойство. Это <xref:System.Windows.Data.Binding> возвращает значение «Fast Value». <xref:System.Windows.Controls.TextBlock> Теперь отображается значение «Fast Value».  
  
 По прошествии 3 секунд `SlowerDP` свойство возвращает значение «Медленнее Value». <xref:System.Windows.Controls.TextBlock> Отображает значение «Медленнее Value».  
  
 По прошествии 5 секунд `SlowestDP` свойство возвращает значение «Самые медленные Value». Эта привязка имеет наивысший приоритет, поскольку он указывается в первую очередь. <xref:System.Windows.Controls.TextBlock> Теперь отображается значение «Самые медленные Value».  
  
 См. в разделе <xref:System.Windows.Data.PriorityBinding> сведения о того, что считается успешной возвращаемое значение из привязки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
