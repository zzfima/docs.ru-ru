---
title: "Практическое руководство. Получение копии для записи объекта Freezable только для чтения | Microsoft Docs"
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
  - "клонирование объектов Freezable"
  - "Freezable - объекты, изменяемые клоны"
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Получение копии для записи объекта Freezable только для чтения
В этом примере демонстрируется использование метода <xref:System.Windows.Freezable.Clone%2A> для создания копии для записи объекта <xref:System.Windows.Freezable> только для чтения.  
  
 После того как объекту <xref:System.Windows.Freezable> будет присвоена пометка «только для чтения» \(«зафиксирован»\), его нельзя изменять.  Тем не менее, можно использовать метод <xref:System.Windows.Freezable.Clone%2A> для создания изменяемой копии зафиксированного объекта.  
  
## Пример  
 В следующем примере создается изменяемая точная копия зафиксированного объекта <xref:System.Windows.Media.SolidColorBrush>.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.Freezable> содержатся в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## См. также  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)