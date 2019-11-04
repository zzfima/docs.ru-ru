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
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="0778c-102">Как реализовать CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="0778c-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="0778c-103">Пример</span><span class="sxs-lookup"><span data-stu-id="0778c-103">Example</span></span>  
 <span data-ttu-id="0778c-104">В следующем примере показано, как отобразить несколько коллекций и элементов в одном списке с помощью класса <xref:System.Windows.Data.CompositeCollection>.</span><span class="sxs-lookup"><span data-stu-id="0778c-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="0778c-105">В этом примере `GreekGods` является <xref:System.Collections.ObjectModel.ObservableCollection%601>ом `GreekGod` пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="0778c-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="0778c-106">Шаблоны данных определяются таким образом, чтобы `GreekGod` объекты и `GreekHero` объекты отображались с золотым и голубым цветами соответственно.</span><span class="sxs-lookup"><span data-stu-id="0778c-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0778c-107">См. также</span><span class="sxs-lookup"><span data-stu-id="0778c-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="0778c-108">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="0778c-108">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="0778c-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="0778c-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
