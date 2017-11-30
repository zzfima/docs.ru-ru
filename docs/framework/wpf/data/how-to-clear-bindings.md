---
title: "Практическое руководство. Очистка привязок"
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
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f8e009d00960f40abcd3c3913a15fa51f1be4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clear-bindings"></a>Практическое руководство. Очистка привязок
В этом примере показано, как удалять привязки к объекту.  
  
## <a name="example"></a>Пример  
 Чтобы удалить привязку из отдельного свойства объекта, вызовите <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> как показано в следующем примере. Следующий пример удаляет привязку из <xref:System.Windows.Controls.TextBlock.TextProperty> из *mytext*, <xref:System.Windows.Controls.TextBlock> объекта.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Очистка привязки удаляет привязку так, что значение свойства зависимостей изменяется на то значение, которое было бы без привязки. Это значение может быть значением по умолчанию, унаследованным или значением из привязки шаблона данных.  
  
 Чтобы очистить привязки от всех возможных свойств объекта, используйте <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.BindingOperations>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
