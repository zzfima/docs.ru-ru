---
title: "Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a9da292b5f65ea9dc44b47a8c3bc13cf43e83b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="819f9-102">Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="819f9-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="819f9-103">Windows Forms <xref:System.Windows.Forms.ListView> элемент управления может отображать дополнительный текст или подэлементы, для каждого элемента в представлении Details.</span><span class="sxs-lookup"><span data-stu-id="819f9-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="819f9-104">В первом столбце отображается текст элемента, например номер сотрудника.</span><span class="sxs-lookup"><span data-stu-id="819f9-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="819f9-105">Второй, третий и последующих столбцах отображаются первый, второй и последующие связанные подэлементы.</span><span class="sxs-lookup"><span data-stu-id="819f9-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="819f9-106">Чтобы добавить дополнительные элементы в элемент списка</span><span class="sxs-lookup"><span data-stu-id="819f9-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="819f9-107">Добавьте все необходимые столбцы.</span><span class="sxs-lookup"><span data-stu-id="819f9-107">Add any columns needed.</span></span> <span data-ttu-id="819f9-108">Так как в первом столбце будет отображаться элемент <xref:System.Windows.Forms.ListView.Text%2A> свойства, необходимо один столбец больше, чем количество дополнительных элементов.</span><span class="sxs-lookup"><span data-stu-id="819f9-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="819f9-109">Дополнительные сведения о добавлении столбцов см. в разделе [как: Добавление столбцов в элемент управления Windows Forms ListView](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="819f9-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="819f9-110">Вызовите <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> метод в коллекцию, возвращаемую <xref:System.Windows.Forms.ListViewItem.SubItems%2A> свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="819f9-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="819f9-111">В примере кода задает имя сотрудника и отдел для элемента списка.</span><span class="sxs-lookup"><span data-stu-id="819f9-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="819f9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="819f9-112">See Also</span></span>  
 [<span data-ttu-id="819f9-113">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="819f9-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="819f9-114">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="819f9-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="819f9-115">Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="819f9-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="819f9-116">Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="819f9-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="819f9-117">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="819f9-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
