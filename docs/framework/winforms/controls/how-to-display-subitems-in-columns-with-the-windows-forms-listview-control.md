---
title: Как выполнить Отображение дополнительных данных в столбцы с помощью элемента управления ListView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: bd41dda048aadc399c7f8ffe0926b010991d08a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686755"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="46a8e-102">Как выполнить Отображение дополнительных данных в столбцы с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46a8e-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="46a8e-103">Windows Forms <xref:System.Windows.Forms.ListView> элемент управления может отображать дополнительный текст или дополнительные элементы, для каждого элемента в представлении сведений.</span><span class="sxs-lookup"><span data-stu-id="46a8e-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="46a8e-104">В первом столбце отображается текст элемента, например код сотрудника.</span><span class="sxs-lookup"><span data-stu-id="46a8e-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="46a8e-105">Второй, третий и последующих столбцах отображаются первый, второй и последующие связанные подэлементы.</span><span class="sxs-lookup"><span data-stu-id="46a8e-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="46a8e-106">Чтобы добавить дополнительные элементы в элемент списка</span><span class="sxs-lookup"><span data-stu-id="46a8e-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="46a8e-107">Добавьте все необходимые столбцы.</span><span class="sxs-lookup"><span data-stu-id="46a8e-107">Add any columns needed.</span></span> <span data-ttu-id="46a8e-108">Поскольку первый столбец будет отображаться элемента <xref:System.Windows.Forms.ListView.Text%2A> свойство, требуется один столбец больше, чем количество дополнительных элементов.</span><span class="sxs-lookup"><span data-stu-id="46a8e-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="46a8e-109">Дополнительные сведения о добавлении столбцов см. в разделе [как: Добавление столбцов в Windows Forms элемента управления ListView](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="46a8e-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="46a8e-110">Вызовите <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> метод из коллекции, возвращаемой <xref:System.Windows.Forms.ListViewItem.SubItems%2A> свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="46a8e-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="46a8e-111">В примере кода ниже задает employee name и department для элемента списка.</span><span class="sxs-lookup"><span data-stu-id="46a8e-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="46a8e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="46a8e-112">See also</span></span>
- [<span data-ttu-id="46a8e-113">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="46a8e-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [<span data-ttu-id="46a8e-114">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46a8e-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="46a8e-115">Практическое руководство. Добавить столбцы для элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46a8e-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="46a8e-116">Практическое руководство. Отображение значков для элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46a8e-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="46a8e-117">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="46a8e-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
