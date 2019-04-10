---
title: Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: ef44a9e68b8007d57fc7442a178ae98322747c99
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343679"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="fdf0b-102">Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdf0b-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="fdf0b-103">Можно добавить элементы Windows Forms <xref:System.Windows.Forms.DomainUpDown> элемента управления в коде.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="fdf0b-104">Вызовите <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класса для добавления элементов к элементу управления <xref:System.Windows.Forms.DomainUpDown.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="fdf0b-105"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Метод добавляет элемент в конец коллекции, хотя <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод добавляет элемент в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="fdf0b-106">Чтобы добавить новый элемент</span><span class="sxs-lookup"><span data-stu-id="fdf0b-106">To add a new item</span></span>  
  
1. <span data-ttu-id="fdf0b-107">Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> метод, чтобы добавить элемент в конец списка элементов.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="fdf0b-108">-или-</span><span class="sxs-lookup"><span data-stu-id="fdf0b-108">-or-</span></span>  
  
2. <span data-ttu-id="fdf0b-109">Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод для вставки элемента в списке в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fdf0b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fdf0b-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fdf0b-111">Элемент управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="fdf0b-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="fdf0b-112">Общие сведения об элементе управления DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="fdf0b-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
