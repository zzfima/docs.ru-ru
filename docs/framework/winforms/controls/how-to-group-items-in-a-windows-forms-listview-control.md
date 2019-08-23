---
title: Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: b4cd2b9ed23f377912270d33b1415ad39c9e80c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966634"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="3be75-102">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3be75-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="3be75-103">С помощью функции <xref:System.Windows.Forms.ListView> группирования элемента управления можно отображать связанные наборы элементов в группах.</span><span class="sxs-lookup"><span data-stu-id="3be75-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="3be75-104">Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп.</span><span class="sxs-lookup"><span data-stu-id="3be75-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="3be75-105">Группы можно использовать <xref:System.Windows.Forms.ListView> для упрощения навигации по большим спискам путем группировки элементов по алфавиту, по датам или по любой другой логической группировке.</span><span class="sxs-lookup"><span data-stu-id="3be75-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="3be75-106">На следующем рисунке показаны некоторые сгруппированные элементы.</span><span class="sxs-lookup"><span data-stu-id="3be75-106">The following image shows some grouped items.</span></span>  
  
 ![Снимок экрана с четными и даже группами ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="3be75-108">Чтобы включить группирование, необходимо сначала создать одну или несколько групп либо в конструкторе, либо программно.</span><span class="sxs-lookup"><span data-stu-id="3be75-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="3be75-109">После определения группы можно назначить <xref:System.Windows.Forms.ListView> элементы группам.</span><span class="sxs-lookup"><span data-stu-id="3be75-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="3be75-110">Можно также перемещать элементы из одной группы в другую программным способом.</span><span class="sxs-lookup"><span data-stu-id="3be75-110">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3be75-111"><xref:System.Windows.Forms.ListView>группы доступны только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] том случае, <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> если приложение вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="3be75-111"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3be75-112">В более ранних операционных системах любой код, связанный с группами, не оказывает никакого влияния, и группы не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="3be75-112">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="3be75-113">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3be75-113">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="3be75-114">Добавление групп</span><span class="sxs-lookup"><span data-stu-id="3be75-114">To add groups</span></span>  
  
1. <span data-ttu-id="3be75-115">Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="3be75-115">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="3be75-116">Удаление групп</span><span class="sxs-lookup"><span data-stu-id="3be75-116">To remove groups</span></span>  
  
1. <span data-ttu-id="3be75-117"><xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> или<xref:System.Windows.Forms.ListView.Groups%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="3be75-117">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="3be75-118">Метод удаляет одну группу <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> ; метод удаляет все группы из списка. <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A></span><span class="sxs-lookup"><span data-stu-id="3be75-118">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3be75-119">При удалении группы элементы в этой группе не удаляются.</span><span class="sxs-lookup"><span data-stu-id="3be75-119">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="3be75-120">Назначение элементов группам или перемещение элементов между группами</span><span class="sxs-lookup"><span data-stu-id="3be75-120">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="3be75-121"><xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> Задайте свойство отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="3be75-121">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="3be75-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3be75-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="3be75-123">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="3be75-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="3be75-124">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="3be75-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="3be75-125">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3be75-125">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
