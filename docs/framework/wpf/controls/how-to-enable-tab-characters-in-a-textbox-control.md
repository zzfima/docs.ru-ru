---
title: "Практическое руководство. Включение знаков табуляции в элементе управления TextBox | Microsoft Docs"
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
  - "Табуляция - знаки, включение"
  - "TextBox - элемент управления, включение знаков табуляции"
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Включение знаков табуляции в элементе управления TextBox
В этом примере показано включение принятия знаков табуляции в качестве обычных входных данных в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 Чтобы включить принятие знаков табуляции в качестве входных данных в элементе управления <xref:System.Windows.Controls.TextBox>, установите атрибут <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> в значение **true**.  
  
 [!code-xml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)