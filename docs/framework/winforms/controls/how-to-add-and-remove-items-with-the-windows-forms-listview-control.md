---
title: "Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms | Microsoft Docs"
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
  - "представления списков, добавление элементов списка"
  - "ListView - элемент управления [Windows Forms], добавление элементов списка"
  - "ListView - элемент управления [Windows Forms], заполнение"
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms
Процесс добавления элемента в элемент управления Windows Forms <xref:System.Windows.Forms.ListView> включает в первую очередь определение элемента и назначение ему свойств.  Добавление и удаление элементов списка может быть выполнено в любое время.  
  
### Программное добавление элементов  
  
1.  Используйте метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> свойства <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### Чтобы удалить элементы программными средствами  
  
1.  Используйте метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> свойства <xref:System.Windows.Forms.ListView.Items%2A>.  Метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> удаляет отдельный элемент, а метод <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> удаляет все элементы из списка.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)