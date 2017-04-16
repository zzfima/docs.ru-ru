---
title: "Практическое руководство. Управление элементами потокового содержимого через свойство Blocks | Microsoft Docs"
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
  - "Blocks - свойство, управления элементами растягиваемого содержимого"
  - "документы, управление элементами растягиваемого содержимого с помощью свойства Blocks"
  - "элементы растягиваемого содержимого, управление с помощью свойства Blocks"
  - "свойства, Blocks, управления элементами растягиваемого содержимого"
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Управление элементами потокового содержимого через свойство Blocks
В этих примерах показаны некоторые наиболее распространенные операции, которые могут быть выполнены в элементах потока содержимого с помощью свойства **Blocks**.  Это свойство используется для добавления и удаления элементов в <xref:System.Windows.Documents.BlockCollection>.  К элементам потока содержимого, которые имеют свойство **Block**, относятся:  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 В этих примерах показано, как использовать <xref:System.Windows.Documents.Section> в качестве элемента потокового содержимого, но эти методы применяются ко всем элементам, в которых размещена коллекция элементов потокового содержимого.  
  
## Пример  
 В следующем примере создается новый <xref:System.Windows.Documents.Section> и затем используется метод **Add** для добавления нового абзаца в содержимое **Section**.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## Пример  
 В следующем примере создается новый элемент <xref:System.Windows.Documents.Paragraph>, который вставляется в начало объекта <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## Пример  
 В следующем примере извлекается число элементов <xref:System.Windows.Documents.Block> верхнего уровня, содержащихся в <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## Пример  
 В следующем примере удаляется последний элемент <xref:System.Windows.Documents.Block> в объекте <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## Пример  
 В следующем примере удаляется все содержимое \(элементы <xref:System.Windows.Documents.Block>\) из объекта <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## См. также  
 <xref:System.Windows.Documents.BlockCollection>   
 <xref:System.Windows.Documents.InlineCollection>   
 <xref:System.Windows.Documents.ListItemCollection>   
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Управление столбцами таблицы с помощью свойства Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)