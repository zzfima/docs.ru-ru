---
title: Практическое руководство. Сортировка и группировка данных с помощью представления в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460129"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="6ccaf-102">Практическое руководство. Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="6ccaf-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="6ccaf-103">В этом примере показано, как создать представление коллекции данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ccaf-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="6ccaf-104">Представления обеспечивают функциональные возможности группирования, сортировки, фильтрации и понятия текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="6ccaf-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ccaf-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6ccaf-105">Example</span></span>  
 <span data-ttu-id="6ccaf-106">В следующем примере статический ресурс с именем *Places* определяется как коллекция объектов *Place* , в которых каждый объект- *место* состоит из названия города и состояния.</span><span class="sxs-lookup"><span data-stu-id="6ccaf-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="6ccaf-107">Префикс *src* сопоставляется с пространством *имен, в котором определены источники данных* .</span><span class="sxs-lookup"><span data-stu-id="6ccaf-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="6ccaf-108">Префикс *SCM* сопоставляется с картами `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* для `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="6ccaf-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="6ccaf-109">В следующем примере создается представление коллекции данных, которая сортируется по названию города и группируются по состоянию.</span><span class="sxs-lookup"><span data-stu-id="6ccaf-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="6ccaf-110">Представление может быть источником привязки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6ccaf-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="6ccaf-111">Для привязок к XML-данным, определенным в <xref:System.Windows.Data.XmlDataProvider> ресурсе, перед именем XML следует указывать символ @.</span><span class="sxs-lookup"><span data-stu-id="6ccaf-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="6ccaf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6ccaf-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="6ccaf-113">Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="6ccaf-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="6ccaf-114">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="6ccaf-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6ccaf-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="6ccaf-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
