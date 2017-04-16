---
title: "Практическое руководство. Включение обрезки текста | Microsoft Docs"
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
  - "документы, усечение текста"
  - "текст, фильтрация"
  - "усечение текста"
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Включение обрезки текста
В этом примере демонстрируется использование и влияние значений, доступных в перечислении <xref:System.Windows.TextTrimming>.  
  
## Пример  
 В следующем примере определяется элемент <xref:System.Windows.Controls.TextBlock> с установленным атрибутом <xref:System.Windows.Controls.TextBlock.TextTrimming%2A>.  
  
 [!code-xml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## Пример  
 Установка соответствующего свойства <xref:System.Windows.TextTrimming> в коде описана ниже.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 В настоящее время существует три варианта обрезки текста: **CharacterEllipsis**, **WordEllipsis** и **None**.  
  
 Если для атрибута <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> установлено значение **CharacterEllipsis**, то текст обрезается и продолжается многоточием после символа, ближайшего к краю обрезки.  При выборе этого параметра текст обрезается ближе к границе обрезки, при этом слова могут быть частично обрезаны.  На следующем рисунке показано влияние этого параметра на элемент <xref:System.Windows.Controls.TextBlock>, похожий на определенный выше.  
  
 ![Пример: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming\_Character")  
  
 Если для атрибута <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> установлено значение **WordEllipsis**, то текст обрезается и продолжается многоточием после первого полного слова, ближайшего к краю обрезки.  При выборе этого параметра не будут отображаться частично обрезанные слова, но текст обрезается не так близко к краю обрезки, как при установке параметра **CharacterEllipsis**.  На следующем рисунке показано влияние этого параметра на элемент <xref:System.Windows.Controls.TextBlock>, определенный выше.  
  
 ![Пример: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming\_Word")  
  
 Если для атрибута <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> установлено значение **None**, то обрезка текста не выполняется.  В этом случае текст просто обрезается по границе родительского текстового контейнера.  На следующем рисунке показано влияние этого параметра на элемент <xref:System.Windows.Controls.TextBlock>, похожий на определенный выше.  
  
 ![Пример: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming\_None")