---
title: "Практическое руководство. Сортировка и группировка данных с помощью представления в XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c219def87e258a2c9fc1bf4f4867287e6156c59a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="b05a3-102">Практическое руководство. Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="b05a3-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="b05a3-103">В этом примере показано, как создать представление набора данных в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b05a3-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="b05a3-104">Представления предоставляют функциональные возможности группирования, сортировки, фильтрации и понятие текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="b05a3-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b05a3-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b05a3-105">Example</span></span>  
 <span data-ttu-id="b05a3-106">В следующем примере статический ресурс с именем *помещает* определяется как совокупность *месте* объектов, в котором каждый *месте* объект состоит из названия города и состояние.</span><span class="sxs-lookup"><span data-stu-id="b05a3-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="b05a3-107">Префикс *src* пространство имен, где источник данных *местах* определен.</span><span class="sxs-lookup"><span data-stu-id="b05a3-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="b05a3-108">Префикс *scm* сопоставляется `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` и *dat* сопоставляется `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="b05a3-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="b05a3-109">В следующем примере создается представление коллекции данных, отсортированных по названию города и сгруппированных по состоянию.</span><span class="sxs-lookup"><span data-stu-id="b05a3-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="b05a3-110">Представление может быть источником привязки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b05a3-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="b05a3-111">Для привязки к данным XML, определенные в <xref:System.Windows.Data.XmlDataProvider> ресурсов, перед именем XML с символа @.</span><span class="sxs-lookup"><span data-stu-id="b05a3-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="b05a3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b05a3-112">See Also</span></span>  
 <xref:System.Windows.Data.CollectionViewSource>  
 [<span data-ttu-id="b05a3-113">Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="b05a3-113">Get the Default View of a Data Collection</span></span>](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [<span data-ttu-id="b05a3-114">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="b05a3-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b05a3-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="b05a3-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
