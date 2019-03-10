---
title: Практическое руководство. Отображение дополнительных данных в столбцы с помощью элемента управления ListView в Windows Forms
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
ms.openlocfilehash: ecdb16087ff5788723b7d562cebd08551df87deb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713076"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="5a3ba-102">Практическое руководство. Отображение дополнительных данных в столбцы с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a3ba-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="5a3ba-103">Windows Forms <xref:System.Windows.Forms.ListView> элемент управления может отображать дополнительный текст или дополнительные элементы, для каждого элемента в представлении сведений.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="5a3ba-104">В первом столбце отображается текст элемента, например код сотрудника.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="5a3ba-105">Второй, третий и последующих столбцах отображаются первый, второй и последующие связанные подэлементы.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="5a3ba-106">Чтобы добавить дополнительные элементы в элемент списка</span><span class="sxs-lookup"><span data-stu-id="5a3ba-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="5a3ba-107">Добавьте все необходимые столбцы.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-107">Add any columns needed.</span></span> <span data-ttu-id="5a3ba-108">Поскольку первый столбец будет отображаться элемента <xref:System.Windows.Forms.ListView.Text%2A> свойство, требуется один столбец больше, чем количество дополнительных элементов.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="5a3ba-109">Дополнительные сведения о добавлении столбцов см. в разделе [как: Добавление столбцов в Windows Forms элемента управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5a3ba-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="5a3ba-110">Вызовите <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> метод из коллекции, возвращаемой <xref:System.Windows.Forms.ListViewItem.SubItems%2A> свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="5a3ba-111">В примере кода ниже задает employee name и department для элемента списка.</span><span class="sxs-lookup"><span data-stu-id="5a3ba-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="5a3ba-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5a3ba-112">See also</span></span>
- [<span data-ttu-id="5a3ba-113">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="5a3ba-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="5a3ba-114">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a3ba-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5a3ba-115">Практическое руководство. Добавить столбцы для элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a3ba-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5a3ba-116">Практическое руководство. Отображение значков для элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a3ba-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5a3ba-117">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5a3ba-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
