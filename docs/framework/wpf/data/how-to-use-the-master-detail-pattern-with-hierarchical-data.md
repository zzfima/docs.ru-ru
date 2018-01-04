---
title: "Практическое руководство. Использование шаблона \"основной-подчиненный\" с иерархическими данными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e392b47682d1bf53dc31073920bdf212fb7d997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Практическое руководство. Использование шаблона "основной-подчиненный" с иерархическими данными
В этом примере показано, как реализовать сценарий основной подробности.  
  
## <a name="example"></a>Пример  
 В этом примере `LeagueList` — это совокупность `Leagues`. Каждый `League` имеет `Name` и коллекцию `Divisions`и каждый `Division` имеет имя и коллекция `Teams`. Каждый `Team` содержит имя команды.  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Ниже приведен снимок экрана примера. `Divisions` <xref:System.Windows.Controls.ListBox> Автоматически отслеживает выделение в `Leagues` <xref:System.Windows.Controls.ListBox> и отображают соответствующие данные. `Teams` <xref:System.Windows.Controls.ListBox> Отслеживает выбор в двух других <xref:System.Windows.Controls.ListBox> элементов управления.  
  
 ![Образец &#45; пример использования типа detail](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 В этом примере следует обратить внимание на два обстоятельства:  
  
1.  Три <xref:System.Windows.Controls.ListBox> привязать элементы управления с одним источником. Задать <xref:System.Windows.Data.Binding.Path%2A> свойства привязки, чтобы указать, какой уровень данных <xref:System.Windows.Controls.ListBox> для отображения.  
  
2.  Необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойства `true` на <xref:System.Windows.Controls.ListBox> элементов управления, из которого осуществляется отслеживание выбора. Задание этого свойства гарантирует, что выбранный элемент всегда задается как <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Кроме того Если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, он автоматически синхронизирует Выбор и денежные единицы.  
  
 Метод немного отличается при использовании [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных. Пример см. в разделе [использовать шаблон «основной-подробности» с иерархическими данными XML](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
