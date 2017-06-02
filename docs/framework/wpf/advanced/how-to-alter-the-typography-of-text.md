---
title: "Практическое руководство. Изменение оформления текста | Microsoft Docs"
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
  - "Оформление - установка атрибутов"
  - "атрибут оформления, параметр"
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Практическое руководство. Изменение оформления текста
В следующем примере показано, как установить атрибут <xref:System.Windows.Documents.TextElement.Typography%2A> с помощью <xref:System.Windows.Documents.Paragraph> в качестве элемента примера  
  
## Пример  
 [!code-xml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 На следующем рисунке показан результат выполнения этого примера.  
  
 ![Снимок экрана: текст с измененной типографией](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement\_Typog")  
  
 На следующем рисунке показано выполнение похожего примера с типографическими свойствами по умолчанию.  
  
 ![Снимок экрана: текст с измененной типографией](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement\_Typog\_Default")  
  
## Пример  
 В следующем примере показано, как программно задать свойство <xref:System.Windows.Controls.TextBox.Typography%2A>.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## См. также  
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)