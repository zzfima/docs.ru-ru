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
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms
Элементы элемента управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> можно удалить, вызвав метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>. Метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> удаляет конкретный элемент, а метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> удаляет элемент по его позиции.  
  
### <a name="to-remove-an-item"></a>Удаление элемента  
  
- Чтобы удалить элемент по имени, используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     -или-  
  
- Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>, чтобы удалить элемент по его позиции.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [Элемент управления DomainUpDown](domainupdown-control-windows-forms.md)
- [Общие сведения об элементе управления DomainUpDown](domainupdown-control-overview-windows-forms.md)
