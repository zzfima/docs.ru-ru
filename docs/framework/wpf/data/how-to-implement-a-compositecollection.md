---
title: Как реализовать CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: f8af8d806b8c889be11533392ee3c831399e9ab7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556121"
---
# <a name="how-to-implement-a-compositecollection"></a>Как реализовать CompositeCollection
## <a name="example"></a>Пример  
 В следующем примере показано, как отображать несколько коллекций и элементов как один список с помощью <xref:System.Windows.Data.CompositeCollection> класса. В этом примере `GreekGods` — <xref:System.Collections.ObjectModel.ObservableCollection%601> из `GreekGod` пользовательских объектов. Шаблоны данных определены, чтобы `GreekGod` объектов и `GreekHero` объекты отображаются с желтым и голубой цвет, соответственно.  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
