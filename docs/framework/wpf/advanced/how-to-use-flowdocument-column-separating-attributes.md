---
title: "Практическое руководство. Использование атрибутов разделения столбцов FlowDocument"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e4a300acccd0c6915844c988a4bbc81426f90f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Практическое руководство. Использование атрибутов разделения столбцов FlowDocument
В этом примере показано, как использовать возможности разделения столбцов <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется <xref:System.Windows.Documents.FlowDocument>и задает <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> атрибуты.  <xref:System.Windows.Documents.FlowDocument> Содержит один абзац содержимого образца.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 На следующем рисунке показано влияние <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> атрибуты в готовом для просмотра <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Снимок экрана: Документ нефиксированного формата внутренний столбец](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")
