---
title: Элементы группы в управлении ListView
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
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141995"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="15eb3-102">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15eb3-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="15eb3-103">С функцией группировки <xref:System.Windows.Forms.ListView> элемента управления можно отображать связанные наборы элементов в группах.</span><span class="sxs-lookup"><span data-stu-id="15eb3-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="15eb3-104">Эти группы разделены на экране горизонтальными заголовками групп, содержащими названия групп.</span><span class="sxs-lookup"><span data-stu-id="15eb3-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="15eb3-105">Группы <xref:System.Windows.Forms.ListView> можно использовать для облегчения навигации по большим спискам, группируя элементы в алфавитном порядке, по дате или по любой другой логической группировке.</span><span class="sxs-lookup"><span data-stu-id="15eb3-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="15eb3-106">На следующем изображении показаны некоторые сгруппированные элементы.</span><span class="sxs-lookup"><span data-stu-id="15eb3-106">The following image shows some grouped items.</span></span>  
  
 ![Скриншот нечетных и четных групп ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 <span data-ttu-id="15eb3-108">Для обеспечения группировки необходимо сначала создать одну или несколько групп в составе дизайнера или в программном плане.</span><span class="sxs-lookup"><span data-stu-id="15eb3-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="15eb3-109">После определения группы можно назначить <xref:System.Windows.Forms.ListView> элементы группам.</span><span class="sxs-lookup"><span data-stu-id="15eb3-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="15eb3-110">Вы также можете перемещать элементы из одной группы в другую в программном плане.</span><span class="sxs-lookup"><span data-stu-id="15eb3-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="15eb3-111">Добавление групп</span><span class="sxs-lookup"><span data-stu-id="15eb3-111">To add groups</span></span>  
  
1. <span data-ttu-id="15eb3-112">Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="15eb3-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="15eb3-113">Удаление групп</span><span class="sxs-lookup"><span data-stu-id="15eb3-113">To remove groups</span></span>  
  
1. <span data-ttu-id="15eb3-114">Используйте <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> или метод <xref:System.Windows.Forms.ListView.Groups%2A> сбора.</span><span class="sxs-lookup"><span data-stu-id="15eb3-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="15eb3-115">Метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> удаляет одну группу; <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> метод удаляет все группы из списка.</span><span class="sxs-lookup"><span data-stu-id="15eb3-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="15eb3-116">Удаление группы не удаляет элементы в этой группе.</span><span class="sxs-lookup"><span data-stu-id="15eb3-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="15eb3-117">Назначать элементы группам или перемещать элементы между группами</span><span class="sxs-lookup"><span data-stu-id="15eb3-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="15eb3-118">Установите <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> свойство отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="15eb3-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="15eb3-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15eb3-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="15eb3-120">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="15eb3-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="15eb3-121">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="15eb3-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="15eb3-122">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15eb3-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
