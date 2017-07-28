---
title: "Практическое руководство. Получение элемента ListBoxItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ListBox - элементы управления, получение ListBoxItem"
  - "ListBoxItem"
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Получение элемента ListBoxItem
Если требуется получить некоторый элемент <xref:System.Windows.Controls.ListBoxItem> с определенным индексом из списка <xref:System.Windows.Controls.ListBox>, можно использовать средство <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
## Пример  
 В следующем примере показан список <xref:System.Windows.Controls.ListBox> и его элементы.  
  
 [!code-xml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 В следующем примере продемонстрировано, как извлечь элемент по индексу в свойстве <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> класса <xref:System.Windows.Controls.ItemContainerGenerator>.  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 После получения элемента списка, можно отобразить содержимое элемента, как показано в следующем примере.  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]