---
title: "Практическое руководство. Добавление в элемент управления ListView возможностей поиска | Microsoft Docs"
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
  - "представления списков, включение поиска"
  - "списки, включение поиска"
  - "ListView - элемент управления [Windows Forms], добавление возможностей поиска"
  - "поиск, добавление в элемент управления ListView возможностей поиска"
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Добавление в элемент управления ListView возможностей поиска
Иногда при работе с крупными списками элементов в элементе управления <xref:System.Windows.Forms.ListView> необходимо предоставить пользователям возможности поиска.  Элемент управления <xref:System.Windows.Forms.ListView> обеспечивает такую функцию двумя способами: поиск совпадений текста и поиск расположений.  
  
 Метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A> позволяет выполнять текстовый поиск в элементе управления <xref:System.Windows.Forms.ListView> в представлении списка или таблицы при наличии строки поиска и необязательного начального и конечного индекса.  Метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A> позволяет находить элементы в <xref:System.Windows.Forms.ListView> в представлении значков или эскизов при наличии координат по вертикали и по горизонтали, а также направления поиска.  
  
### Чтобы найти элемент с помощью текста  
  
1.  Создайте элемент управления <xref:System.Windows.Forms.ListView> со свойством <xref:System.Windows.Forms.ListView.View%2A>, равным <xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>, затем заполните <xref:System.Windows.Forms.ListView> элементами.  
  
2.  Вызовите метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A> передав текст элемента, который нужно найти.  
  
3.  В следующем примере кода показано, как создать простой элемент управления <xref:System.Windows.Forms.ListView>, наполнить его элементами и использовать введенный пользователем текст для поиска элемента в списке.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### Чтобы найти элемент с помощью координат по горизонтали и вертикали  
  
1.  Создайте элемент управления <xref:System.Windows.Forms.ListView> со свойством <xref:System.Windows.Forms.View>, равным <xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>, затем заполните <xref:System.Windows.Forms.ListView> элементами.  
  
2.  Вызовите метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A>, передав нужные координаты по горизонтали и вертикали, а также нужное направление поиска.  
  
3.  В следующем примере кода показано, как создать простой значок <xref:System.Windows.Forms.ListView>, наполнить его элементами и захватить событие <xref:System.Windows.Forms.Control.MouseDown>, Чтобы найти ближайший элемент в направлении вверх.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>   
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)