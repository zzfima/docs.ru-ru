---
title: "Практическое руководство. Управление элементами потокового содержимого через свойство Inlines | Microsoft Docs"
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
  - "документы, управление элементами растягиваемого содержимого с помощью свойства Inlines"
  - "элементы растягиваемого содержимого, управление с помощью свойства Inlines"
  - "Inlines - свойство, управления элементами растягиваемого содержимого"
  - "свойства, Inlines, управления элементами растягиваемого содержимого"
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Управление элементами потокового содержимого через свойство Inlines
В следующих примерах демонстрируются некоторые из наиболее распространенных операций, которые могут выполняться над встроенными элементами потокового содержимого \(и контейнерами таких элементов, например <xref:System.Windows.Controls.TextBlock>\) через свойство **Inlines**.  Это свойство используется для добавления и удаления элементов в <xref:System.Windows.Documents.InlineCollection>.  Элементы потокового содержимого, которые имеют свойство **Inlines**:  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 В этих примерах показано, как использовать <xref:System.Windows.Documents.Span> в качестве элемента потокового содержимого, но эти методы применяются ко всем элементам или элементам управления, в которых размещена коллекция <xref:System.Windows.Documents.InlineCollection>.  
  
## Пример  
 В следующем примере создается новый объект <xref:System.Windows.Documents.Span>, а затем вызывается метод **Добавить** для добавления двух текстовых выполнений в качестве содержимого дочернего объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## Пример  
 В следующем примере создается новый элемент <xref:System.Windows.Documents.Run>, который вставляется в начало объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## Пример  
 В следующем примере извлекается число элементов <xref:System.Windows.Documents.Inline> верхнего уровня, содержащихся в <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## Пример  
 В следующем примере удаляется последний элемент <xref:System.Windows.Documents.Inline> в объекте <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## Пример  
 В следующем примере удаляется все содержимое \(элементы <xref:System.Windows.Documents.Inline>\) из объекта <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## См. также  
 <xref:System.Windows.Documents.BlockCollection>   
 <xref:System.Windows.Documents.InlineCollection>   
 <xref:System.Windows.Documents.ListItemCollection>   
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Управление FlowDocument через свойство блоков](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Управление столбцами таблицы с помощью свойства Columns](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [Управление группами строк таблицы пользователя с помощью свойства RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)