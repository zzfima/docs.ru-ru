---
title: Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 702e5e2180148758c4b3775a5cc96a1365703166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532165"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms
Можно удалить элементы из Windows Forms <xref:System.Windows.Forms.DomainUpDown> управления путем вызова <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класса. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> Метод удаляет конкретный элемент, пока <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> метод удаляет элемент с указанной позицией.  
  
### <a name="to-remove-an-item"></a>Удаление элемента  
  
-   Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класса, чтобы удалить элемент по имени.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     - или -  
  
-   Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> метод, чтобы удалить элемент с указанной позицией.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [Элемент управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [Общие сведения об элементе управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
