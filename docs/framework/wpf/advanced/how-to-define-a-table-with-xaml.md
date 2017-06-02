---
title: "Практическое руководство. Определение таблицы с помощью XAML | Microsoft Docs"
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
  - "документы, определение таблиц в XAML"
  - "таблицы, определение в XAML"
  - "XAML, определение таблиц"
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Определение таблицы с помощью XAML
В приведенном ниже примере показано, как определить таблицу <xref:System.Windows.Documents.Table> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Таблица в примере содержит четыре столбца \(представленных элементами <xref:System.Windows.Documents.TableColumn>\) и несколько строк \(представленных элементами <xref:System.Windows.Documents.TableRow>\), содержащих данные, а также название, заголовок и нижний колонтитул.  Строки должны содержаться в элементе <xref:System.Windows.Documents.TableRowGroup>.  Каждая строка в таблице состоит из одной или нескольких ячеек \(представленных элементами <xref:System.Windows.Documents.TableCell>\).  Содержимое ячейки таблицы должно содержаться в элементе <xref:System.Windows.Documents.Block>; в данном случае используются элементы <xref:System.Windows.Documents.Paragraph>.  В таблице содержится также гиперссылка \(представленная элементом <xref:System.Windows.Documents.Hyperlink>\) в строке нижнего колонтитула.  
  
## Пример  
 [!code-xml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 На следующем рисунке показано, как отображается таблица, определенная в данном примере.  
  
 ![Отображенная таблица.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")