---
title: "Практическое руководство. сделать объект Freezable доступным только для чтения"
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
helpviewer_keywords: Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa6d3f7109e8258dff0a07556bc8572f6071c961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-freezable-read-only"></a>Практическое руководство. сделать объект Freezable доступным только для чтения
В этом примере показано, как сделать <xref:System.Windows.Freezable> только для чтения, вызвав его <xref:System.Windows.Freezable.Freeze%2A> метод.  
  
 Невозможно закрепить <xref:System.Windows.Freezable> объекта, если выполнено одно из следующих условий является `true` об объекте:  
  
-   Объект имеет анимированные или свойства с привязкой к данным.  
  
-   Он имеет свойства, которые задаются динамический ресурс. Дополнительные сведения о динамических ресурсах см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Он содержит <xref:System.Windows.Freezable> подчиненных объектах, которые нельзя зафиксировать.  
  
 Если эти условия выполняются `false` для вашей <xref:System.Windows.Freezable> объекта и вы не собираетесь изменять, можно зафиксировать, чтобы получить выигрыш в производительности.  
  
## <a name="example"></a>Пример  
 В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush>, который является типом <xref:System.Windows.Freezable> объекта.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Дополнительные сведения о <xref:System.Windows.Freezable> объектов, в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
