---
title: "Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], добавление к элементам управления ListView"
  - "представления списков, добавление столбцов"
  - "ListView - элемент управления [Windows Forms], добавление заголовков столбцов"
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms
В представлении "Подробности" элемент управления <xref:System.Windows.Forms.ListView> может отображать несколько столбцов для каждого элемента списка.  Можно использовать столбцы для отображения пользователю нескольких типов данных о каждом элементе списка.  Например, в списке файлов можно отображать имя файла, его типа, размер и дату последнего изменения файла.  Сведения о заполнении столбцов после их создания содержатся в разделе [Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### Чтобы добавить столбцы с помощью программных средств  
  
1.  Присвойте свойству <xref:System.Windows.Forms.ListView.View%2A> элемента управления значение <xref:System.Windows.Forms.View>.  
  
2.  Используйте метод <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> свойства представления в виде списка <xref:System.Windows.Forms.ListView.Columns%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)