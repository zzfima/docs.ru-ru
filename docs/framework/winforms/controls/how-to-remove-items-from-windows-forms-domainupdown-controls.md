---
title: Удаление элементов из элементов управления DomainUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735766"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="e97c4-102">Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e97c4-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="e97c4-103">Элементы элемента управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> можно удалить, вызвав метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>.</span><span class="sxs-lookup"><span data-stu-id="e97c4-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="e97c4-104">Метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> удаляет конкретный элемент, а метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> удаляет элемент по его позиции.</span><span class="sxs-lookup"><span data-stu-id="e97c4-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="e97c4-105">Удаление элемента</span><span class="sxs-lookup"><span data-stu-id="e97c4-105">To remove an item</span></span>  
  
- <span data-ttu-id="e97c4-106">Чтобы удалить элемент по имени, используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>.</span><span class="sxs-lookup"><span data-stu-id="e97c4-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="e97c4-107">\- или -</span><span class="sxs-lookup"><span data-stu-id="e97c4-107">-or-</span></span>  
  
- <span data-ttu-id="e97c4-108">Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>, чтобы удалить элемент по его позиции.</span><span class="sxs-lookup"><span data-stu-id="e97c4-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e97c4-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="e97c4-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e97c4-110">Элемент управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e97c4-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="e97c4-111">Общие сведения об элементе управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e97c4-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
