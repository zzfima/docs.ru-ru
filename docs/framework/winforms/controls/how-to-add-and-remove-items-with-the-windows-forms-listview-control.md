---
title: Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 83ef2e108695988bbb0329d9f01e1317d9308f18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525659"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="2c0a4-102">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c0a4-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="2c0a4-103">Процесс добавления элемента в форму Windows Forms <xref:System.Windows.Forms.ListView> управления состоит в определение элемента и назначение ему свойств.</span><span class="sxs-lookup"><span data-stu-id="2c0a4-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="2c0a4-104">Добавление или удаление элементов списка может выполняться в любое время.</span><span class="sxs-lookup"><span data-stu-id="2c0a4-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="2c0a4-105">Чтобы добавить элементы программными средствами</span><span class="sxs-lookup"><span data-stu-id="2c0a4-105">To add items programmatically</span></span>  
  
1.  <span data-ttu-id="2c0a4-106">Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="2c0a4-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="2c0a4-107">Чтобы удалить элементы программными средствами</span><span class="sxs-lookup"><span data-stu-id="2c0a4-107">To remove items programmatically</span></span>  
  
1.  <span data-ttu-id="2c0a4-108">Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="2c0a4-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="2c0a4-109"><xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> Метод удаляет один элемент; <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод удаляет все элементы из списка.</span><span class="sxs-lookup"><span data-stu-id="2c0a4-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="2c0a4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2c0a4-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="2c0a4-111">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="2c0a4-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="2c0a4-112">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="2c0a4-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
