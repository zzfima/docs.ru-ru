---
title: Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459143"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
В простом сценарии "основной/подробности" имеется <xref:System.Windows.Controls.ItemsControl> с привязкой к данным, например <xref:System.Windows.Controls.ListBox>. На основе выбора пользователя отображаются дополнительные сведения о выбранном элементе. В этом примере показано, как реализовать этот сценарий.  
  
## <a name="example"></a>Пример  
 В этом примере `People` является <xref:System.Collections.ObjectModel.ObservableCollection%601> классов `Person`. Этот `Person` класс содержит три свойства: `FirstName`, `LastName`и `HomeTown`, все типы `string`.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl> использует следующие <xref:System.Windows.DataTemplate>, определяющие, каким образом отображаются сведения о `Person`.  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Ниже приведен снимок экрана, в котором создается пример. В <xref:System.Windows.Controls.ContentControl> отображаются другие свойства выбранного человека.  
  
 ![Привязка к коллекции](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 В этом примере необходимо обратить внимание на два момента:  
  
1. <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ContentControl> привязываются к одному и тому же источнику. Свойства <xref:System.Windows.Data.Binding.Path%2A> обеих привязок не указаны, так как оба элемента управления привязаны ко всему объекту коллекции.  
  
2. Чтобы это работало, необходимо задать для свойства <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true`. Задание этого свойства гарантирует, что выбранный элемент всегда будет установлен в качестве <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Кроме того, если <xref:System.Windows.Controls.ListBox> получает данные из <xref:System.Windows.Data.CollectionViewSource>, она автоматически синхронизирует выбор и валют.  
  
 Обратите внимание, что класс `Person` переопределяет метод `ToString` следующим образом. По умолчанию <xref:System.Windows.Controls.ListBox> вызывает `ToString` и отображает строковое представление каждого объекта в привязанной коллекции. Именно поэтому каждый `Person` отображается как имя в <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>См. также

- [Использование шаблона "Основной/подробности" с иерархическими данными](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Использование шаблона "Основной/подробности" с иерархическими XML-данными](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](data-templating-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
