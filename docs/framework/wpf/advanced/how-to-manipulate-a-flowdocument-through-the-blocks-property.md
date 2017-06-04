---
title: "Практическое руководство. Управление FlowDocument через свойство блоков | Microsoft Docs"
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
  - "Blocks - свойство, управление FlowDocument"
  - "документы, управление FlowDocument с помощью свойства Blocks"
  - "FlowDocument, управление с помощью свойства Blocks"
  - "свойства, Blocks, управление FlowDocument"
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Управление FlowDocument через свойство блоков
Эти примеры демонстрируют некоторые наиболее распространенные операции, которые могут выполняться на <xref:System.Windows.Documents.FlowDocument> с использованием свойства <xref:System.Windows.Documents.FlowDocument.Blocks%2A>.  
  
## Пример  
 В следующем примере создается новый <xref:System.Windows.Documents.FlowDocument>, а затем добавляется новый элемент <xref:System.Windows.Documents.Paragraph> к <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## Пример  
 В следующем примере создается новый элемент <xref:System.Windows.Documents.Paragraph>, который вставляется в начало объекта <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## Пример  
 В следующем примере извлекается число элементов <xref:System.Windows.Documents.Block> верхнего уровня, содержащихся в <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## Пример  
 В следующем примере удаляется последний элемент <xref:System.Windows.Documents.Block> в объекте <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## Пример  
 В следующем примере удаляется все содержимое \(элементы <xref:System.Windows.Documents.Block>\) из объекта <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## См. также  
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Управление столбцами таблицы с помощью свойства Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)