---
title: "Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms | Microsoft Docs"
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
  - "Представление "Сведения""
  - "элементы списка"
  - "ListView - элемент управления [Windows Forms], добавление ListSubItems"
  - "подэлементы"
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms
В режиме представления "Таблица" для каждого элемента в элементе управления Windows Forms <xref:System.Windows.Forms.ListView> может отображаться дополнительный текст или подэлементы.  В первом столбце отображается текст элемента, например номер сотрудника.  Во втором, третьем и последующих столбцах отображаются первый, второй и последующие связанные подэлементы.  
  
### Добавление подэлементов в элемент списка  
  
1.  Добавьте все необходимые столбцы.  Поскольку в первом столбце будет отображаться свойство <xref:System.Windows.Forms.ListView.Text%2A> элемента, потребуется на один столбец больше, чем количество подэлементов.  Дополнительные сведения о добавлении столбцов см. в разделе [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2.  Вызовите метод <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> коллекции, возвращаемой свойством <xref:System.Windows.Forms.ListViewItem.SubItems%2A> элемента.  В приведенном ниже примере кода для элемента списка задается имя сотрудника и отдел.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## См. также  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)