---
title: "Практическое руководство. Изменение свойства TextWrapping программными средствами | Microsoft Docs"
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
  - "документы, программное изменение свойства TextWrapping"
  - "TextWrapping - свойство, программное изменение"
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Изменение свойства TextWrapping программными средствами
## Пример  
 В следующем примере показано, как изменить значение свойства <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> программным способом.  
  
 В элементе <xref:System.Windows.Controls.StackPanel> кода [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] размещены три элемента <xref:System.Windows.Controls.Button>. Каждое событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> элемента управления <xref:System.Windows.Controls.Button> соответствует обработчику событий в коде.  Имена обработчиков событий совпадают со значением <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>, которое применяется к `txt2` при нажатии кнопки.  Также текст в `txt1` \(<xref:System.Windows.Controls.TextBlock> не отображается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\) обновляется для отражения изменений свойства.  
  
 [!code-xml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>   
 <xref:System.Windows.TextWrapping>