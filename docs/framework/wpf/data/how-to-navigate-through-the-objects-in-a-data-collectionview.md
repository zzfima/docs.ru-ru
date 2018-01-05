---
title: "Практическое руководство. Перемещение по объектам в Data CollectionView"
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
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215e3583d50567a2bfec8226e006bc7398628299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="ba2b6-102">Практическое руководство. Перемещение по объектам в Data CollectionView</span><span class="sxs-lookup"><span data-stu-id="ba2b6-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="ba2b6-103">Представления позволяют просматривать различными способами, в зависимости от сортировки, фильтрации и группирования же коллекцию данных.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="ba2b6-104">Представления также предоставляют понятием текущего указателя записи и включают перемещение указателя.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="ba2b6-105">В этом примере показано, как получить текущий объект, а также перемещение по объектам в коллекции данных, используя функциональные возможности, предоставляемые <xref:System.Windows.Data.CollectionView> класса.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba2b6-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ba2b6-106">Example</span></span>  
 <span data-ttu-id="ba2b6-107">В этом примере `myCollectionView` — <xref:System.Windows.Data.CollectionView> объект, который является представлением присоединенной коллекции.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="ba2b6-108">В следующем примере `OnButton` является обработчиком событий для `Previous` и `Next` кнопки в приложении, которые находятся кнопки, позволяющие пользователю перемещаться по коллекции данных.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="ba2b6-109">Обратите внимание, что <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> и <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> свойства отчета, является ли указатель текущей записи поступило в начало и конец списка соответственно таким образом, <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> и <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> могут быть вызваны соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="ba2b6-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A> Свойства представления приводится к `Order` для возврата текущего элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ba2b6-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="ba2b6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ba2b6-111">See Also</span></span>  
 [<span data-ttu-id="ba2b6-112">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="ba2b6-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ba2b6-113">Сортировка данных в представлении</span><span class="sxs-lookup"><span data-stu-id="ba2b6-113">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="ba2b6-114">Фильтрация данных в представлении</span><span class="sxs-lookup"><span data-stu-id="ba2b6-114">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="ba2b6-115">Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="ba2b6-115">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="ba2b6-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ba2b6-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
