---
title: "Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms | Microsoft Docs"
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
  - "группирование"
  - "группы"
  - "группы, в элементах управления Windows Forms"
  - "представления списков, группирование элементов"
  - "списки, группирование элементов"
  - "ListView - элемент управления [Windows Forms], группирование элементов"
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms
Функция группирования элемента управления <xref:System.Windows.Forms.ListView> позволяет отображать соответствующие наборы элементов в виде групп.  Эти группы разделяются на экране горизонтальными заголовками группы, которые содержат названия групп.  Можно использовать группы <xref:System.Windows.Forms.ListView> для упрощения просмотра больших списков за счет группирования их элементов по алфавиту, по дате или по другим критериям.  На приведенном ниже рисунке показаны некоторые сгруппированные элементы.  
  
 ![Группы ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
Сгруппированные элементы ListView  
  
 Для разрешения группирования необходимо сначала создать одну или несколько групп в конструкторе или программным путем.  После определения группы можно назначить группам элементы <xref:System.Windows.Forms.ListView>.  Элементы можно также перемещать между группами программным путем.  
  
> [!NOTE]
>  Группы <xref:System.Windows.Forms.ListView> можно использовать только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] при вызове приложением метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  В предыдущих версиях операционных систем код, связанный с созданием групп, не действует, и группы отображаться не будут.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>.  
  
### Добавление групп  
  
1.  Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### Удаление групп  
  
1.  Используйте метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> коллекции <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     Метод <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> удаляет отдельную группу, а метод <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> удаляет все группы из списка.  
  
    > [!NOTE]
    >  При удалении группы, элементы из группы не удаляются.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### Назначение элементов группам и перемещение элементов между группами  
  
1.  Установите свойство <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=fullName> для отдельных элементов.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ru-ru/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)