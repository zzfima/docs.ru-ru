---
title: Практическое руководство. Использование шаблона "главный-подчиненный" с иерархическими данными
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 41f02013feb1405e5640afa73b954dc84921c924
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351487"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Практическое руководство. Использование шаблона "главный-подчиненный" с иерархическими данными
В этом примере показано, как для реализации сценария «основной-подробности».  
  
## <a name="example"></a>Пример  
 В этом примере `LeagueList` — это коллекция `Leagues`. Каждый `League` имеет `Name` и коллекцию `Divisions`и каждый `Division` имеет имя и коллекция `Teams`. Каждый `Team` содержит имя команды.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Ниже приведен снимок экрана примера. `Divisions` <xref:System.Windows.Controls.ListBox> Автоматически отслеживает выделение в `Leagues` <xref:System.Windows.Controls.ListBox> и отображают соответствующие данные. `Teams` <xref:System.Windows.Controls.ListBox> Отслеживает выбранные параметры в двух других <xref:System.Windows.Controls.ListBox> элементов управления.  
  
 ![Главный&#45;пример использования типа detail](./media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 В этом примере следует обратить внимание на два обстоятельства:  
  
1.  Три <xref:System.Windows.Controls.ListBox> привязать элементы управления с одним источником. Можно задать <xref:System.Windows.Data.Binding.Path%2A> свойство привязки, чтобы указать, какой уровень данных <xref:System.Windows.Controls.ListBox> для отображения.  
  
2.  Необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойства `true` на <xref:System.Windows.Controls.ListBox> элементов управления, из которых осуществляется отслеживание выбора. Задание этого свойства гарантирует, что выбранный элемент всегда задается как <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Кроме того Если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, он автоматически синхронизирует Выбор и денежные единицы.  
  
 Метод немного отличается при использовании [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных. Например, см. в разделе [использование шаблона «основной-подробности» с иерархическими данными XML](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.HierarchicalDataTemplate>
- [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Общие сведения о шаблонах данных](data-templating-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
