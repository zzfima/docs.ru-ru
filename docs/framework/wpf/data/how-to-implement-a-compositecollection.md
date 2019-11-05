---
title: Как реализовать CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454030"
---
# <a name="how-to-implement-a-compositecollection"></a>Как реализовать CompositeCollection
## <a name="example"></a>Пример  
 В следующем примере показано, как отобразить несколько коллекций и элементов в одном списке с помощью класса <xref:System.Windows.Data.CompositeCollection>. В этом примере `GreekGods` является <xref:System.Collections.ObjectModel.ObservableCollection%601>ом `GreekGod` пользовательских объектов. Шаблоны данных определяются таким образом, чтобы `GreekGod` объекты и `GreekHero` объекты отображались с золотым и голубым цветами соответственно.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
