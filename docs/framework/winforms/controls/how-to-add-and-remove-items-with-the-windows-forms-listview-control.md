---
title: Добавление и удаление элементов с помощью элемента управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: bbfe99db857ebe3a80bf99926f3ce0bec38a1f3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743138"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="8d25a-102">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d25a-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="8d25a-103">Процесс добавления элемента в элемент управления Windows Forms <xref:System.Windows.Forms.ListView> состоит главным образом из указания элемента и присвоения ему свойств.</span><span class="sxs-lookup"><span data-stu-id="8d25a-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="8d25a-104">Добавление или удаление элементов списка можно выполнить в любое время.</span><span class="sxs-lookup"><span data-stu-id="8d25a-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="8d25a-105">Добавление элементов программным способом</span><span class="sxs-lookup"><span data-stu-id="8d25a-105">To add items programmatically</span></span>  
  
1. <span data-ttu-id="8d25a-106">Используйте метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> свойства <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d25a-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="8d25a-107">Удаление элементов программным способом</span><span class="sxs-lookup"><span data-stu-id="8d25a-107">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="8d25a-108">Используйте метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> свойства <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d25a-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="8d25a-109">Метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> удаляет один элемент. метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> удаляет все элементы из списка.</span><span class="sxs-lookup"><span data-stu-id="8d25a-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="8d25a-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d25a-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="8d25a-111">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="8d25a-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="8d25a-112">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="8d25a-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
