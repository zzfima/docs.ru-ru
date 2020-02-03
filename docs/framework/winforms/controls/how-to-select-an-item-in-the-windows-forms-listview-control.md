---
title: Выбор элемента в элементе управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743234"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="2b7be-102">Практическое руководство. Выделение строки элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b7be-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="2b7be-103">В этом примере показано, как программным способом выбрать элемент в элементе управления Windows Forms <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="2b7be-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="2b7be-104">При выборе элемента программным способом не происходит автоматического переключения фокуса на элемент управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="2b7be-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="2b7be-105">По этой причине, как правило, требуется задать элемент в качестве элемента, который будет заменяться при выборе элемента.</span><span class="sxs-lookup"><span data-stu-id="2b7be-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b7be-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2b7be-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b7be-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2b7be-107">Compiling the Code</span></span>  
 <span data-ttu-id="2b7be-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="2b7be-108">This example requires:</span></span>  
  
- <span data-ttu-id="2b7be-109">Элемент управления <xref:System.Windows.Forms.ListView> с именем `listView1`, содержащий по крайней мере один элемент.</span><span class="sxs-lookup"><span data-stu-id="2b7be-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="2b7be-110">Ссылки на пространства имен <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b7be-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7be-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2b7be-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
