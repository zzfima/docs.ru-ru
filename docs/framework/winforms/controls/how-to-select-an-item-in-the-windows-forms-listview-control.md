---
title: Практическое руководство. Выделение строки элемента управления ListView в Windows Forms
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
ms.openlocfilehash: b3cfcc6c2873dfb0eb95cf7950adc6b2bb73e74c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143186"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="fa9db-102">Практическое руководство. Выделение строки элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa9db-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="fa9db-103">В этом примере показано, как программно выбрать элемент в формах Windows <xref:System.Windows.Forms.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fa9db-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="fa9db-104">Выбор элемента программным образом не изменяется автоматически фокуса в <xref:System.Windows.Forms.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fa9db-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="fa9db-105">По этой причине обычно необходимо также задать элемент как с фокусом ввода при выделении элемента.</span><span class="sxs-lookup"><span data-stu-id="fa9db-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa9db-106">Пример</span><span class="sxs-lookup"><span data-stu-id="fa9db-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa9db-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fa9db-107">Compiling the Code</span></span>  
 <span data-ttu-id="fa9db-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="fa9db-108">This example requires:</span></span>  
  
-   <span data-ttu-id="fa9db-109">Объект <xref:System.Windows.Forms.ListView> управления с именем `listView1` , содержащий хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="fa9db-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="fa9db-110">Ссылки на пространства имен <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa9db-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9db-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fa9db-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
