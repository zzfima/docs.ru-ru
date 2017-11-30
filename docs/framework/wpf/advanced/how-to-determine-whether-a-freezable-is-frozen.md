---
title: "Практическое руководство. Определение состояния объекта класса Freezable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47fb0a871c3792450386c440629ead1ee3fbecdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>Практическое руководство. Определение состояния объекта класса Freezable
В этом примере показано, как определить, является ли <xref:System.Windows.Freezable> объект заморожен. При попытке изменения зафиксированного <xref:System.Windows.Freezable> объекта, он вызывает <xref:System.InvalidOperationException>. Чтобы избежать возникновения этого исключения, используйте <xref:System.Windows.Freezable.IsFrozen%2A> свойство <xref:System.Windows.Freezable> объекта, чтобы определить, зафиксирован ли он.  
  
## <a name="example"></a>Пример  
 В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush> и затем проверяется с помощью <xref:System.Windows.Freezable.IsFrozen%2A> свойства, чтобы определить, зафиксирован ли он.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Дополнительные сведения о <xref:System.Windows.Freezable> объектов, в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
