---
title: "Практическое руководство. Реализация пользовательского механизма размещения элементов управления в форме | Microsoft Docs"
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
  - "FlowLayoutPanel - элемент управления [Windows Forms], обработчик макета"
  - "обработчики макетов, пользовательский"
  - "обработчики макетов, реализация"
  - "LayoutEngine - класс"
  - "TableLayoutPanel - элемент управления [Windows Forms], обработчик макета"
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Реализация пользовательского механизма размещения элементов управления в форме
В следующем примере кода демонстрируется способ создания пользовательского механизма размещения элементов управления, обеспечивающего одномерную компоновку формы.  В нем реализован элемент управления типа "панель" с именем `DemoFlowPanel`, переопределяющий свойство <xref:System.Windows.Forms.Control.LayoutEngine%2A> и предоставляющий таким образом экземпляр класса `DemoFlowLayout`.  
  
## Пример  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## См. также  
 <xref:System.Windows.Forms.Layout.LayoutEngine>   
 <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=fullName>