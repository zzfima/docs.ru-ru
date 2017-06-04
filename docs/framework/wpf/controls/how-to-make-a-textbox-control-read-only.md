---
title: "Практическое руководство. Перевод элемента управления TextBox в режим только для чтения | Microsoft Docs"
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
  - "защищенные от записи элементы управления TextBox"
  - "защищенный от записи элемент управления TextBox"
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Перевод элемента управления TextBox в режим только для чтения
В этом примере показано, как настроить элемент управления <xref:System.Windows.Controls.TextBox>, чтобы запретить пользовательский ввод или изменение.  
  
## Пример  
 Чтобы запретить пользователям изменение содержимого элемента управления <xref:System.Windows.Controls.TextBox>, следует установить атрибут <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> в значение **true**.  
  
 [!code-xml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 Атрибут <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> относится только к пользовательскому вводу и не влияет на текст, установленный в описании [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] элемента управления <xref:System.Windows.Controls.TextBox>, или текст, установленный программными средствами с помощью свойства <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 Значением <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> по умолчанию является **false**.  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)