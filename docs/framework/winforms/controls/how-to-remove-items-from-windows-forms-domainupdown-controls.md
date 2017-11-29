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
  
     -или-  
  
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
