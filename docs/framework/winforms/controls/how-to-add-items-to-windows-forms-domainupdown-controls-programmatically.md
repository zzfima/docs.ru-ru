---
title: Практическое руководство. Добавление элементов управления DomainUpDown Windows Forms программными средствами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 06c2c83ddfba67aaff775065cc2aa4515978bf81
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722715"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="e91fd-102">Практическое руководство. Добавление элементов управления DomainUpDown Windows Forms программными средствами</span><span class="sxs-lookup"><span data-stu-id="e91fd-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="e91fd-103">Можно добавить элементы Windows Forms <xref:System.Windows.Forms.DomainUpDown> элемента управления в коде.</span><span class="sxs-lookup"><span data-stu-id="e91fd-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="e91fd-104">Вызовите <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класса для добавления элементов к элементу управления <xref:System.Windows.Forms.DomainUpDown.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e91fd-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="e91fd-105"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Метод добавляет элемент в конец коллекции, хотя <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод добавляет элемент в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="e91fd-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="e91fd-106">Чтобы добавить новый элемент</span><span class="sxs-lookup"><span data-stu-id="e91fd-106">To add a new item</span></span>  
  
1.  <span data-ttu-id="e91fd-107">Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> метод, чтобы добавить элемент в конец списка элементов.</span><span class="sxs-lookup"><span data-stu-id="e91fd-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="e91fd-108">- или -</span><span class="sxs-lookup"><span data-stu-id="e91fd-108">-or-</span></span>  
  
2.  <span data-ttu-id="e91fd-109">Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод для вставки элемента в списке в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="e91fd-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e91fd-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e91fd-110">See also</span></span>
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e91fd-111">Элемент управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e91fd-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="e91fd-112">Общие сведения об элементе управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e91fd-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
