---
title: "Практическое руководство. Привязка элемента ListBox к данным | Microsoft Docs"
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
  - "привязка данных, к элементу управления ListBox"
  - "привязка данных, ListBox - элемент управления"
  - "ListBox - элементы управления, привязка данных"
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Привязка элемента ListBox к данным
Разработчики приложений могут создавать элементы управления <xref:System.Windows.Controls.ListBox> без указания содержимого каждого элемента <xref:System.Windows.Controls.ListBoxItem> отдельно.  Можно использовать связывание данных для привязки данных к отдельным элементам.  
  
 В следующем примере показано, как создать список <xref:System.Windows.Controls.ListBox>, заполняющий элементы <xref:System.Windows.Controls.ListBoxItem> через привязку данных к источнику данных *Цвета*.  В этом случае необязательно использовать теги <xref:System.Windows.Controls.ListBoxItem> для указания содержимого каждого элемента.  
  
## Пример  
 [!code-xml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## См. также  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.Controls.ListBoxItem>   
 [Элементы управления](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)