---
title: Практическое руководство. Реализация CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091169"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="d59b1-102">Практическое руководство. Реализация CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="d59b1-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="d59b1-103">Пример</span><span class="sxs-lookup"><span data-stu-id="d59b1-103">Example</span></span>  
 <span data-ttu-id="d59b1-104">В следующем примере показано, как отображать несколько коллекций и элементов как один список с помощью <xref:System.Windows.Data.CompositeCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="d59b1-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="d59b1-105">В этом примере `GreekGods` — <xref:System.Collections.ObjectModel.ObservableCollection%601> из `GreekGod` пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="d59b1-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="d59b1-106">Шаблоны данных определены таким образом, чтобы `GreekGod` объектов и `GreekHero` объекты отображаются с желтым и голубой цвет, соответственно.</span><span class="sxs-lookup"><span data-stu-id="d59b1-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d59b1-107">См. также</span><span class="sxs-lookup"><span data-stu-id="d59b1-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="d59b1-108">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="d59b1-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="d59b1-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="d59b1-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
