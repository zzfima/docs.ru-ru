---
title: "Практическое руководство. Извлечение текстового содержимого из элемента управления RichTextBox | Microsoft Docs"
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
  - "содержание, извлечение"
  - "извлечение текстового содержимого"
  - "RichTextBox - элемент управления, извлечение текстового содержимого"
  - "текстовое содержимое, извлечение"
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Извлечение текстового содержимого из элемента управления RichTextBox
В этом примере демонстрируется способ извлечения содержимого <xref:System.Windows.Controls.RichTextBox> в виде обычного текста.  
  
## Пример  
 В следующем коде [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] описывается элемент управления <xref:System.Windows.Controls.RichTextBox> с простым содержимым.  
  
 [!code-xml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## Пример  
 Следующий код реализует метод, который принимает <xref:System.Windows.Controls.RichTextBox> в качестве аргумента и возвращает строку, представляющую текстовое содержимое <xref:System.Windows.Controls.RichTextBox>.  
  
 Метод создает новый объект <xref:System.Windows.Documents.TextRange> из содержимого <xref:System.Windows.Controls.RichTextBox> с помощью свойств <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> и <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> для указания диапазона извлекаемого содержимого.  Каждое из свойств <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> и <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> возвращает <xref:System.Windows.Documents.TextPointer> и доступно в основном FlowDocument, представляющем содержимое <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> предоставляет свойство Text, которое возвращает часть обычного текста <xref:System.Windows.Documents.TextRange> в виде строки.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## См. также  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)