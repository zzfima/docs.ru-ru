---
title: Группирование элементов в элементе управления ListView
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
ms.openlocfilehash: 45846751780f433c29b186fe8b9a908f5d295ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736624"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="57ef5-102">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57ef5-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="57ef5-103">Функция группирования элемента управления <xref:System.Windows.Forms.ListView> позволяет отображать связанные наборы элементов в группах.</span><span class="sxs-lookup"><span data-stu-id="57ef5-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="57ef5-104">Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп.</span><span class="sxs-lookup"><span data-stu-id="57ef5-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="57ef5-105">Вы можете использовать группы <xref:System.Windows.Forms.ListView>, чтобы упростить навигацию по большим спискам, группируя элементы по алфавиту, по датам или по любой другой логической группировке.</span><span class="sxs-lookup"><span data-stu-id="57ef5-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="57ef5-106">На следующем рисунке показаны некоторые сгруппированные элементы.</span><span class="sxs-lookup"><span data-stu-id="57ef5-106">The following image shows some grouped items.</span></span>  
  
 ![Снимок экрана с четными и даже группами ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="57ef5-108">Чтобы включить группирование, необходимо сначала создать одну или несколько групп либо в конструкторе, либо программно.</span><span class="sxs-lookup"><span data-stu-id="57ef5-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="57ef5-109">После определения группы можно назначить элементы <xref:System.Windows.Forms.ListView> группам.</span><span class="sxs-lookup"><span data-stu-id="57ef5-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="57ef5-110">Можно также перемещать элементы из одной группы в другую программным способом.</span><span class="sxs-lookup"><span data-stu-id="57ef5-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="57ef5-111">Добавление групп</span><span class="sxs-lookup"><span data-stu-id="57ef5-111">To add groups</span></span>  
  
1. <span data-ttu-id="57ef5-112">Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="57ef5-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="57ef5-113">Удаление групп</span><span class="sxs-lookup"><span data-stu-id="57ef5-113">To remove groups</span></span>  
  
1. <span data-ttu-id="57ef5-114">Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="57ef5-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="57ef5-115">Метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> удаляет одну группу; метод <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> удаляет все группы из списка.</span><span class="sxs-lookup"><span data-stu-id="57ef5-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="57ef5-116">При удалении группы элементы в этой группе не удаляются.</span><span class="sxs-lookup"><span data-stu-id="57ef5-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="57ef5-117">Назначение элементов группам или перемещение элементов между группами</span><span class="sxs-lookup"><span data-stu-id="57ef5-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="57ef5-118">Задайте свойство <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="57ef5-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="57ef5-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="57ef5-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="57ef5-120">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="57ef5-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="57ef5-121">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="57ef5-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="57ef5-122">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57ef5-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
