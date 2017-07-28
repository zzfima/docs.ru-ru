---
title: "Практическое руководство. Установка текстового содержимого для элемента управления TextBox | Microsoft Docs"
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
  - "текстовое содержимое, параметр"
  - "TextBox - элемент управления, установка текстового содержимого"
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Установка текстового содержимого для элемента управления TextBox
В этом примере описывается порядок использования свойства <xref:System.Windows.Controls.TextBox.Text%2A> для установки начального текстового содержимого элемента управления <xref:System.Windows.Controls.TextBox>.  
  
 **Примечание.** Хотя в версии примера на [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] содержимое поля <xref:System.Windows.Controls.TextBox> каждой кнопки и можно заключать в теги`<TextBox.Text>`, это не обязательно, поскольку <xref:System.Windows.Controls.TextBox> применяет к свойству <xref:System.Windows.Controls.TextBox.Text%2A> атрибут <xref:System.Windows.Markup.ContentPropertyAttribute>.  Дополнительные сведения см. в разделе [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
## Пример  
 [!code-xml[TextBox_MiscCode#_TextBoxSetTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## Пример  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)