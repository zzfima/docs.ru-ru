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
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms
Элементы можно добавлять в Windows Forms элемент управления <xref:System.Windows.Forms.DomainUpDown> в коде. Вызовите метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>, чтобы добавить элементы в свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> элемента управления. Метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> добавляет элемент в конец коллекции, а метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> добавляет элемент в указанную позицию.  
  
### <a name="to-add-a-new-item"></a>Добавление нового элемента  
  
1. Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>, чтобы добавить элемент в конец списка элементов.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     \- или -  
  
2. Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>, чтобы вставить элемент в список в указанной позиции.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [Элемент управления DomainUpDown](domainupdown-control-windows-forms.md)
- [Общие сведения об элементе управления DomainUpDown](domainupdown-control-overview-windows-forms.md)
