---
title: "Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a751025470b566ef1e735e4ddd192cfd8fc354ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
В простом сценарии подробный имеют привязкой к данным <xref:System.Windows.Controls.ItemsControl> например <xref:System.Windows.Controls.ListBox>. На основе выбора пользователя, можно отобразить дополнительные сведения о выбранном элементе. В этом примере показано, как реализовать этот сценарий.  
  
## <a name="example"></a>Пример  
 В этом примере `People` — <xref:System.Collections.ObjectModel.ObservableCollection%601> из `Person` классы. Это `Person` класс содержит три свойства: `FirstName`, `LastName`, и `HomeTown`, все типа `string`.  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl> Использует следующие <xref:System.Windows.DataTemplate> определяет, как данные `Person` представлены:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Ниже приведен снимок экрана примера. <xref:System.Windows.Controls.ContentControl> Отображает свойства выбранного лица.  
  
 ![Привязка к коллекции](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 В этом примере следует обратить внимание на два обстоятельства:  
  
1.  <xref:System.Windows.Controls.ListBox> И <xref:System.Windows.Controls.ContentControl> привязку к тому же источнику. <xref:System.Windows.Data.Binding.Path%2A> Свойства обе привязки не указаны, так как оба элемента управления привязаны к объекту коллекции.  
  
2.  Необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойства `true` для правильной работы. Задание этого свойства гарантирует, что выбранный элемент всегда задается как <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. Кроме того Если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, он автоматически синхронизирует Выбор и денежные единицы.  
  
 Обратите внимание, что `Person` класса переопределения `ToString` метод следующим образом. По умолчанию <xref:System.Windows.Controls.ListBox> вызовы `ToString` и отображает строковое представление каждого объекта в привязанной коллекции. Поэтому каждый `Person` отображается как имя в <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>См. также  
 [Использование шаблона "Основной/подробности" с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [Использование шаблона "Основной/подробности" с иерархическими XML-данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
