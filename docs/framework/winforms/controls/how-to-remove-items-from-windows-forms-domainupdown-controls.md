---
title: "Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DomainUpDown - элемент управления [Windows Forms], удаление элементов из"
  - "счетчик - элемент управления, удаление элементов"
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms
Вызвав метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>, можно удалить элементы из элемента управления Windows Forms <xref:System.Windows.Forms.DomainUpDown>.  Метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> удаляет конкретный элемент, в то время как метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> удаляет элемент, находящийся в определенном месте.  
  
### Удаление элемента  
  
-   Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> для удаления элемента с заданным именем.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     \-или\-  
  
-   Используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> для удаления элемента, расположенного в определенном месте.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=fullName>   
 [Элемент управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [Общие сведения об элементе управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)