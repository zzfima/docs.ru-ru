---
title: "Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms"
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
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaa6c58afa8dd39151f7e19890a6e933d82d049d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms
Элементы добавляются в Windows Forms <xref:System.Windows.Forms.DomainUpDown> элемента управления в коде. Вызовите <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> класс для добавления элементов в элемент управления <xref:System.Windows.Forms.DomainUpDown.Items%2A> свойство. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Метод добавляет элемент в конец коллекции, а <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> метод добавляет элемент в указанной позиции.  
  
### <a name="to-add-a-new-item"></a>Чтобы добавить новый элемент  
  
1.  Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> метод, чтобы добавить элемент в конец списка элементов.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     -или-  
  
2.  Используйте <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> способ вставки элемента в список в указанной позиции.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>  
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>  
 [Элемент управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [Общие сведения об элементе управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
