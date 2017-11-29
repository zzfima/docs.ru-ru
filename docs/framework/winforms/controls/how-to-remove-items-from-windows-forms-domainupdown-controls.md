---
title: "Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms"
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
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cab9bf4445c7322c1b4824f26c0821de8c58657
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="4507e-102">Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4507e-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="4507e-103">Можно удалить элементы из Windows Forms <xref:System.Windows.Forms.DomainUpDown> управления путем вызова <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="4507e-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="4507e-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> Метод удаляет конкретный элемент, пока <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> метод удаляет элемент с указанной позицией.</span><span class="sxs-lookup"><span data-stu-id="4507e-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="4507e-105">Удаление элемента</span><span class="sxs-lookup"><span data-stu-id="4507e-105">To remove an item</span></span>  
  
-   <span data-ttu-id="4507e-106">Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класса, чтобы удалить элемент по имени.</span><span class="sxs-lookup"><span data-stu-id="4507e-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="4507e-107">-или-</span><span class="sxs-lookup"><span data-stu-id="4507e-107">-or-</span></span>  
  
-   <span data-ttu-id="4507e-108">Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> метод, чтобы удалить элемент с указанной позицией.</span><span class="sxs-lookup"><span data-stu-id="4507e-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4507e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4507e-109">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4507e-110">Элемент управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="4507e-110">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [<span data-ttu-id="4507e-111">Общие сведения об элементе управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="4507e-111">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
