---
title: Практическое руководство. Использование шаблона "основной-подчиненный" с иерархическими данными
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733484"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>Практическое руководство. Использование шаблона "основной-подчиненный" с иерархическими данными
В этом примере показано, как реализовать сценарий "основной-подробности".  
  
## <a name="example"></a>Пример  
 В этом примере `LeagueList` является коллекцией `Leagues`. Каждый `League` имеет `Name` и коллекцию `Divisions`, а каждый `Division` имеет имя и коллекцию `Teams`. Каждый `Team` имеет имя команды.  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Ниже приведен снимок экрана примера. `Divisions` <xref:System.Windows.Controls.ListBox> автоматически отслеживает выделенные элементы в `Leagues` <xref:System.Windows.Controls.ListBox> и отображает соответствующие данные. `Teams` <xref:System.Windows.Controls.ListBox> отслеживает выделение в других двух элементах управления <xref:System.Windows.Controls.ListBox>.  
  
 ![Снимок экрана, на котором&#45;показан пример сценария главной детализации.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 В этом примере необходимо обратить внимание на два момента:  
  
1. Три элемента управления <xref:System.Windows.Controls.ListBox> привязываются к одному и тому же источнику. Свойство <xref:System.Windows.Data.Binding.Path%2A> привязки задается, чтобы указать, какой уровень данных будет отображаться в <xref:System.Windows.Controls.ListBox>.  
  
2. Необходимо задать для свойства <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true` в элементах управления <xref:System.Windows.Controls.ListBox>, для которых отслеживается выбранный объект. Задание этого свойства гарантирует, что выбранный элемент всегда будет установлен в качестве <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Кроме того, если <xref:System.Windows.Controls.ListBox> получает данные из <xref:System.Windows.Data.CollectionViewSource>, она автоматически синхронизирует выбор и валют.  
  
 При использовании XML-данных метод слегка отличается. Пример см. в разделе [Использование шаблона "основной/подробности" с иерархическими XML-данными](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.HierarchicalDataTemplate>
- [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](data-templating-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
