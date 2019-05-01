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
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020742"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="dfc85-102">Практическое руководство. Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="dfc85-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="dfc85-103">В этом примере показано, как создать представление для сбора данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfc85-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="dfc85-104">Представления предоставляют функциональные возможности группирования, сортировки, фильтрации и понятие текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="dfc85-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfc85-105">Пример</span><span class="sxs-lookup"><span data-stu-id="dfc85-105">Example</span></span>  
 <span data-ttu-id="dfc85-106">В следующем примере статический ресурс с именем *помещает* определен как коллекция *месте* объектов, в котором каждый *месте* объект состоит из название города и состояние.</span><span class="sxs-lookup"><span data-stu-id="dfc85-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="dfc85-107">Префикс *src* пространство имен, где источник данных *местах* определен.</span><span class="sxs-lookup"><span data-stu-id="dfc85-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="dfc85-108">Префикс *scm* сопоставляется `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* сопоставляется `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="dfc85-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="dfc85-109">В следующем примере создается представление коллекции данных, сгруппированных по состоянию и отсортированы по названию города.</span><span class="sxs-lookup"><span data-stu-id="dfc85-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="dfc85-110">Представление может быть источником привязки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="dfc85-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="dfc85-111">Для привязки к данным XML, определенные в <xref:System.Windows.Data.XmlDataProvider> ресурсов, укажите перед именем XML символ @.</span><span class="sxs-lookup"><span data-stu-id="dfc85-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="dfc85-112">См. также</span><span class="sxs-lookup"><span data-stu-id="dfc85-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="dfc85-113">Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="dfc85-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="dfc85-114">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="dfc85-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="dfc85-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="dfc85-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
