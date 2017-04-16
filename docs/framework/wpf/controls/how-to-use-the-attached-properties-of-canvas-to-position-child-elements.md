---
title: "Практическое руководство. Использование присоединенных свойств Canvas для расположения дочерних элементов | Microsoft Docs"
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
  - "вложенные свойства зависимостей [конструктор WPF]"
  - "Canvas - элемент управления, вложенные свойства"
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Использование присоединенных свойств Canvas для расположения дочерних элементов
В этом примере показано использование [присоединенных свойств](GTMT) <xref:System.Windows.Controls.Canvas> для изменения расположения дочерних элементов.  
  
## Пример  
 В следующем примере четыре элемента <xref:System.Windows.Controls.Button> добавляются в качестве дочерних элементов родительского <xref:System.Windows.Controls.Canvas>.  Каждый дочерний элемент представляет отдельное вложенное свойство <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A> и <xref:System.Windows.Controls.Canvas.Top%2A>.  Каждый <xref:System.Windows.Controls.Button> располагается относительно родительского <xref:System.Windows.Controls.Canvas> согласно своему значению присоединенного свойства.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.Canvas.Bottom%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 <xref:System.Windows.Controls.Canvas.Right%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Button>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)   
 [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)