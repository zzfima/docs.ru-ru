---
title: "Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms | Microsoft Docs"
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
  - "DomainUpDown - элемент управления [Windows Forms], добавление элементов"
  - "счетчик - элемент управления, добавление элементов"
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms
Элементы в элемент управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> можно добавлять в коде.  Вызовите метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> или <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> класса <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>, чтобы добавить элементы в свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> элемента управления.  Метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> добавляет элемент в конец коллекции, в то время как метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> добавляет элемент в конкретное место.  
  
### Добавление нового элемента  
  
1.  Для добавления элемента в конец списка элементов используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     \-или\-  
  
2.  Для вставки элемента в конкретное место данного списка используйте метод <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=fullName>   
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=fullName>   
 [Элемент управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [Общие сведения об элементе управления DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)