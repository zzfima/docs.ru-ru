---
title: "Практическое руководство. Использование атрибутов разделения столбцов FlowDocument | Microsoft Docs"
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
  - "атрибуты разделения столбцов"
  - "документы, FlowDocument - атрибуты разделения столбцов"
  - "FlowDocument - атрибуты разделения столбцов"
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Использование атрибутов разделения столбцов FlowDocument
В этом примере показаны возможности использования разделения столбцов <xref:System.Windows.Documents.FlowDocument>.  
  
## Пример  
 В следующем примере определяется <xref:System.Windows.Documents.FlowDocument> и устанавливаются атрибуты <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A> <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A>.  <xref:System.Windows.Documents.FlowDocument> содержит один абзац содержимого образца.  
  
 [!code-xml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 На следующем рисунке показано влияние атрибутов <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A> <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> на отображаемый <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Снимок экрана: внутренний столбец документа нефиксированного формата](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")