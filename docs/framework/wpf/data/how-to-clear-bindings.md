---
title: "Практическое руководство. Очистка привязок | Microsoft Docs"
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
  - "привязки, очистка"
  - "очистка привязок"
  - "привязка данных, очистка привязок"
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Очистка привязок
В этом примере демонстрируется очистка привязок объекта.  
  
## Пример  
 Чтобы удалить привязку из отдельного свойства объекта, вызовите <xref:System.Windows.Data.BindingOperations.ClearBinding%2A>, как показано в следующем примере.  Следующий пример удаляет привязку из свойства <xref:System.Windows.Controls.TextBlock.TextProperty> *mytext* объекта <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Очистка привязки удаляет привязку таким образом, что значение [свойства зависимости](GTMT) изменяется на то, каким оно было бы без привязки.  Это значение может быть значением по умолчанию, унаследованным значением или значением из привязки шаблона данных.  
  
 Чтобы очистить привязки из всех возможных свойств объекта, используйте <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## См. также  
 <xref:System.Windows.Data.BindingOperations>   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)