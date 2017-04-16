---
title: "Практическое руководство. Определение состояния объекта класса Freezable | Microsoft Docs"
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
  - "Freezable - объекты, определение наличия фиксации"
  - "IsFrozen - свойство"
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Определение состояния объекта класса Freezable
В данном примере показано, как определить, зафиксирован ли объект класса <xref:System.Windows.Freezable>.  Если попытаться изменить зафиксированный объект класса <xref:System.Windows.Freezable>, он вызовет исключение <xref:System.InvalidOperationException>.  Чтобы избежать возникновения данного исключения, необходимо использовать свойство <xref:System.Windows.Freezable.IsFrozen%2A> объекта <xref:System.Windows.Freezable>, чтобы определить, зафиксирован ли он.  
  
## Пример  
 В следующем примере фиксируется объект <xref:System.Windows.Media.SolidColorBrush> и затем с помощью свойства <xref:System.Windows.Freezable.IsFrozen%2A> проверяется является ли он зафиксированным.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Дополнительные сведения об объектах <xref:System.Windows.Freezable> содержатся в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## См. также  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.IsFrozen%2A>   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)