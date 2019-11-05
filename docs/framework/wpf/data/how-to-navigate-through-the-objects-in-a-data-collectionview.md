---
title: Практическое руководство. Перемещение по объектам в Data CollectionView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459702"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Практическое руководство. Перемещение по объектам в Data CollectionView
Представления позволяют просматривать одну и ту же коллекцию данных различными способами в зависимости от сортировки, фильтрации или группирования. Представления также предоставляют концепцию указателя текущей записи и позволяют перемещать указатель. В этом примере показано, как получить текущий объект и перемещаться по объектам в коллекции данных с помощью функциональных возможностей, предоставляемых классом <xref:System.Windows.Data.CollectionView>.  
  
## <a name="example"></a>Пример  
 В этом примере `myCollectionView` является объектом <xref:System.Windows.Data.CollectionView>, который является представлением для привязанной коллекции.  
  
 В следующем примере `OnButton` является обработчиком событий для `Previous` и `Next` кнопок в приложении, которые являются кнопками, позволяющими пользователю перемещаться по коллекции данных. Обратите внимание, что свойства <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> и <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> указывают, поступил ли указатель текущей записи к началу и концу списка соответственно, чтобы <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> и <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> можно было вызывать соответствующим образом.  
  
 Свойство <xref:System.Windows.Data.CollectionView.CurrentItem%2A> представления приводится как `Order` для возврата текущего элемента Order в коллекции.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Сортировка данных в представлении](how-to-sort-data-in-a-view.md)
- [Фильтрация данных в представлении](how-to-filter-data-in-a-view.md)
- [Сортировка и группировка данных с помощью представления в XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
