---
title: "Практическое руководство. Установка фокуса в элементе управления TextBox | Microsoft Docs"
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
  - "фокус, параметр"
  - "TextBox - элемент управления, установка фокуса"
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Установка фокуса в элементе управления TextBox
В этом примере показано использование метода <xref:System.Windows.UIElement.Focus%2A> для установки фокуса на элемент управления <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 Следующий пример [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] описывает простой элемент управления <xref:System.Windows.Controls.TextBox> с именем  *tbFocusMe*  
  
 [!code-xml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## Пример  
 Следующий пример вызывает метод <xref:System.Windows.UIElement.Focus%2A> для установки фокуса на элемент управления <xref:System.Windows.Controls.TextBox> с именем *tbFocusMe*.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## См. также  
 <xref:System.Windows.UIElement.Focusable%2A>   
 <xref:System.Windows.UIElement.IsFocused%2A>   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)