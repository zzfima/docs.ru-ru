---
title: "Практическое руководство. Построение таблицы программным способом | Microsoft Docs"
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
  - "создание, таблиц (программным способом)"
  - "документы, программное создание таблиц"
  - "таблицы, создание программным способом"
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Построение таблицы программным способом
В следующих примерах показано, как программно создать <xref:System.Windows.Documents.Table> и заполнить ее содержимым.  Содержимое таблицы распределено по пяти строкам \(представленным объектами <xref:System.Windows.Documents.TableRow>, содержащимися в объекте <xref:System.Windows.Documents.Table.RowGroups%2A>\) и шести столбцам \(представленным объектами <xref:System.Windows.Documents.TableColumn>\).  Строки используются для различных целей представления, включая строку названия, предназначенную для заголовка всей таблицы, строку заголовка для описания столбцов данных в таблице, и строку нижнего колонтитула для итоговой информации.  Обратите внимание, что строки "название", "заголовок" и "примечания" не встроены в таблицу, а просто являются строками с разными характеристиками.  Ячейки таблицы содержат фактическое содержимое, которое может состоять из текста, изображений или практически любых других элементов [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
## Пример  
 Вначале создается <xref:System.Windows.Documents.FlowDocument> для размещения <xref:System.Windows.Documents.Table>, а также новая таблица <xref:System.Windows.Documents.Table>, в которую добавляется содержимое из <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## Пример  
 Далее с применением некоторого форматирования создаются шесть объектов <xref:System.Windows.Documents.TableColumn>, которые добавляются в коллекцию таблицы <xref:System.Windows.Documents.Table.Columns%2A>.  
  
> [!NOTE]
>  Обратите внимание, что коллекция таблицы <xref:System.Windows.Documents.Table.Columns%2A> использует стандартное индексирование начиная с нуля.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## Пример  
 Далее создается строка названия и добавляется к таблице с применением некоторого форматирования.  Строка названия будет содержать одну ячейку, объединяющую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## Пример  
 Далее создается и добавляется в таблицу строка заголовка, а ее ячейки создаются и заполняются содержимым.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## Пример  
 Далее создается и добавляется в таблицу строка для данных, ячейки этой строки также создаются и заполняются содержимым.  Построение этой строки аналогично построению строки заголовка за исключением слегка отличающегося форматирования.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## Пример  
 После этого создается, добавляется и форматируется строка нижнего колонтитула.  Как и строка названия, нижний колонтитул содержит одну ячейку, объединяющую все шесть столбцов таблицы.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## См. также  
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)