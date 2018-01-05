---
title: "Практическое руководство. Поиск элемента TreeViewItem в TreeView"
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
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 696a9e2d92b9c44e4aedbcc200b41e5548cd7411
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="b248c-102">Практическое руководство. Поиск элемента TreeViewItem в TreeView</span><span class="sxs-lookup"><span data-stu-id="b248c-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="b248c-103"><xref:System.Windows.Controls.TreeView> Элемент управления предоставляет удобный способ отображения иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="b248c-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="b248c-104">Если ваш <xref:System.Windows.Controls.TreeView> привязан к источнику данных, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> свойству предоставляет удобный способ для быстрого извлечения выбранного объекта данных.</span><span class="sxs-lookup"><span data-stu-id="b248c-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="b248c-105">Обычно лучше всего работать с базовым объектом данных, но иногда необходимо программно манипулировать данных, содержащих <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="b248c-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="b248c-106">Например, может потребоваться программно разверните <xref:System.Windows.Controls.TreeViewItem>, или выберите другой элемент в <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="b248c-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="b248c-107">Чтобы найти <xref:System.Windows.Controls.TreeViewItem> , содержащий конкретный объект данных, необходимо пройти каждый уровень <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="b248c-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="b248c-108">Элементы в <xref:System.Windows.Controls.TreeView> также можно виртуализировать для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="b248c-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="b248c-109">В случае, когда виртуализации элементов необходимо также реализовать <xref:System.Windows.Controls.TreeViewItem> Чтобы проверить, содержит ли объект данных.</span><span class="sxs-lookup"><span data-stu-id="b248c-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b248c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b248c-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="b248c-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="b248c-111">Description</span></span>  
 <span data-ttu-id="b248c-112">В следующем примере выполняется поиск <xref:System.Windows.Controls.TreeView> для указанного объекта и возвращает объект, содержащего <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="b248c-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="b248c-113">В примере проверяется, чтобы каждый <xref:System.Windows.Controls.TreeViewItem> создается, чтобы его дочерние элементы можно искать.</span><span class="sxs-lookup"><span data-stu-id="b248c-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="b248c-114">В этом примере также работает, если <xref:System.Windows.Controls.TreeView> используются виртуализированные элементы.</span><span class="sxs-lookup"><span data-stu-id="b248c-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b248c-115">Следующий пример работает для любого <xref:System.Windows.Controls.TreeView>, независимо от базовой модели данных и выполняет каждый <xref:System.Windows.Controls.TreeViewItem> пока объект найден.</span><span class="sxs-lookup"><span data-stu-id="b248c-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="b248c-116">Другим способом, который имеет более высокую производительность является поиск модели данных для указанного объекта, отслеживать его положение в иерархии данных и затем найти соответствующий <xref:System.Windows.Controls.TreeViewItem> в <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="b248c-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="b248c-117">Тем не менее, метод, который имеет более высокую производительность требует знаний модели данных и не может быть обобщена для любой заданной <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="b248c-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="b248c-118">Код</span><span class="sxs-lookup"><span data-stu-id="b248c-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="b248c-119">Предыдущий код использует пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel> , предоставляет метод с именем `BringIntoView`.</span><span class="sxs-lookup"><span data-stu-id="b248c-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="b248c-120">Следующий код определяет пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel>.</span><span class="sxs-lookup"><span data-stu-id="b248c-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="b248c-121">Приведенный ниже код XAML показан способ создания <xref:System.Windows.Controls.TreeView> , использующего пользовательский <xref:System.Windows.Controls.VirtualizingStackPanel>.</span><span class="sxs-lookup"><span data-stu-id="b248c-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b248c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b248c-122">See Also</span></span>  
 [<span data-ttu-id="b248c-123">Повышение производительности элемента управления TreeView</span><span class="sxs-lookup"><span data-stu-id="b248c-123">Improve the Performance of a TreeView</span></span>](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
