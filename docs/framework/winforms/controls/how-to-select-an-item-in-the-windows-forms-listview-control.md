---
title: "Практическое руководство. Выделение строки элемента управления ListView в Windows Forms | Microsoft Docs"
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
  - "представления списков, выделение элементов"
  - "списки, выделение элементов"
  - "ListView - элемент управления [Windows Forms], выделение элементов"
  - "выделенный фрагмент, в представлениях списков"
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Выделение строки элемента управления ListView в Windows Forms
Этом примере показано, как программно выбрать элемент в элементе управления Windows Forms <xref:System.Windows.Forms.ListView>.  При программном выборе элемента фокус не переходит автоматически на элемент управления <xref:System.Windows.Forms.ListView>.  По этой причине при выборе элемента, как правило, нужно задать его как имеющий фокус.  
  
## Пример  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.ListView> с именем `listView1`, содержащий по крайней мере один элемент.  
  
-   Ссылки на пространства имен <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=fullName>