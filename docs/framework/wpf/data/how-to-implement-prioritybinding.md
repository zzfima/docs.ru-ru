---
title: "Практическое руководство. Реализация класса PriorityBinding | Microsoft Docs"
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
  - "классы, PriorityBinding"
  - "привязка данных, PriorityBinding -класс"
  - "PriorityBinding -класс"
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Реализация класса PriorityBinding
Класс <xref:System.Windows.Data.PriorityBinding> в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] работает путем указания списка привязок.  Список привязок упорядочен от наивысшего приоритета к более низкому приоритету.  Если при обработке привязка наивысшего приоритета успешно возвращает значение, то нет необходимости обрабатывать другие привязки в списке.  Это может происходить в том случае, когда выполнение привязки наивысшего приоритета занимает много времени, а следующий высокий приоритет, успешно возвращающий значение, будет использоваться до тех пор, пока привязка более высокого приоритета не вернет значение.  
  
## Пример  
 Для демонстрации работы класса <xref:System.Windows.Data.PriorityBinding> был создан объект `AsyncDataSource` со следующими тремя свойствами: `FastDP`, `SlowerDP` и `SlowestDP`.  
  
 Метод доступа Get свойства `FastDP` возвращает значение члена данных `_fastDP`.  
  
 Метод доступа Get свойства `SlowerDP` ожидает 3 секунды перед возвратом значения члена данных `_slowerDP`.  
  
 Метод доступа Get свойства `SlowestDP` ожидает 5 секунд перед возвратом значения члена данных `_slowestDP`.  
  
> [!NOTE]
>  Этот пример используется только в качестве демонстрации.  Правила [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] рекомендованы для определения свойств, которые на несколько порядков медленнее, чем мог бы быть набор полей.  Дополнительные сведения см. в разделе [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/ru-ru/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Свойство <xref:System.Windows.Controls.TextBlock.Text%2A> привязывается к вышеописанному объекту `AsyncDS` с помощью класса <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Когда обработчик привязки обрабатывает объекты <xref:System.Windows.Data.Binding>, он начинает с первой привязки <xref:System.Windows.Data.Binding>, связанной со свойством `SlowestDP`.  После обработки этой привязки <xref:System.Windows.Data.Binding> он не обеспечивает успешного возвращения значения, поскольку оно находится в состоянии ожидания в течение 5 секунд, поэтому обрабатывается следующий элемент <xref:System.Windows.Data.Binding>.  Следующая привязка <xref:System.Windows.Data.Binding> не обеспечивает успешного возвращения значения, так как она находится в состоянии ожидания в течение 3 секунд.  Затем обработчик привязки перемещается к следующему элементу <xref:System.Windows.Data.Binding>, связанному со свойством `FastDP`.  Эта привязка <xref:System.Windows.Data.Binding> возвращает значение "Fast Value".  Теперь элемент <xref:System.Windows.Controls.TextBlock> отображает значение "Fast Value".  
  
 По прошествии 3 секунд свойство `SlowerDP` возвращает значение "Slower Value".  Затем элемент <xref:System.Windows.Controls.TextBlock> отображает значение "Slower Value".  
  
 По прошествии 5 секунд свойство `SlowestDP` возвращает значение "Slowest Value".  Эта привязка имеет наивысший приоритет, поскольку она указана первой.  Теперь элемент <xref:System.Windows.Controls.TextBlock> отображает значение "Slowest Value".  
  
 См. описание класса <xref:System.Windows.Data.PriorityBinding> для получения сведений об условиях успешного возвращаемого значения привязки.  
  
## См. также  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=fullName>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)