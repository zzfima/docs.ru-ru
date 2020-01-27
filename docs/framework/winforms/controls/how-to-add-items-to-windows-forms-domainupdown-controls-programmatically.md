---
title: Добавление элементов в элементы управления DomainUpDown программными средствами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745590"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="e4da3-102">Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4da3-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="e4da3-103">Элементы можно добавлять в Windows Forms элемент управления <xref:System.Windows.Forms.DomainUpDown> в коде.</span><span class="sxs-lookup"><span data-stu-id="e4da3-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="e4da3-104">Вызовите метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>, чтобы добавить элементы в свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e4da3-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="e4da3-105">Метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> добавляет элемент в конец коллекции, а метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> добавляет элемент в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="e4da3-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="e4da3-106">Добавление нового элемента</span><span class="sxs-lookup"><span data-stu-id="e4da3-106">To add a new item</span></span>  
  
1. <span data-ttu-id="e4da3-107">Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>, чтобы добавить элемент в конец списка элементов.</span><span class="sxs-lookup"><span data-stu-id="e4da3-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="e4da3-108">\- или -</span><span class="sxs-lookup"><span data-stu-id="e4da3-108">-or-</span></span>  
  
2. <span data-ttu-id="e4da3-109">Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>, чтобы вставить элемент в список в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="e4da3-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e4da3-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="e4da3-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e4da3-111">Элемент управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e4da3-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="e4da3-112">Общие сведения об элементе управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e4da3-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
