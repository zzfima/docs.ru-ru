---
title: "Изменение выделения в RichTextBox программными средствами | Microsoft Docs"
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
  - "изменение выделений в RichTextBox [WPF]"
  - "изменение выделений в текстовом поле [WPF]"
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Изменение выделения в RichTextBox программными средствами
В этом примере демонстрируется программное изменение текущего выделения в <xref:System.Windows.Controls.RichTextBox>.  Это выделение является таким же, как если бы пользователь выделил содержимое с помощью интерфейса пользователя.  
  
## Пример  
 В следующем коде [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] описывается элемент управления <xref:System.Windows.Controls.RichTextBox> с простым содержимым.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## Пример  
 В следующем коде программно выбирается произвольный текст при щелчке мыши внутри <xref:System.Windows.Controls.RichTextBox>.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## См. также  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)