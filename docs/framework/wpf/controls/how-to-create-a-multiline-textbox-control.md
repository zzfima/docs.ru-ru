---
title: "Как создать элемент управления для нескольких TextBox | Microsoft Docs"
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
  - "TextBox - элемент управления, несколько строк текста"
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Как создать элемент управления для нескольких TextBox
В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], чтобы определить элемент управления <xref:System.Windows.Controls.TextBox>, который будет автоматически расширяться, чтобы вместить несколько строк текста.  
  
## Пример  
 Установка атрибута <xref:System.Windows.Controls.TextBox.TextWrapping%2A> **Wrap** вызовет перенос вводимого текста на новую строку при достижении края элемента управления <xref:System.Windows.Controls.TextBox>, автоматически расширяя элемент управления <xref:System.Windows.Controls.TextBox>, чтобы включить место для новой строки, при необходимости.  
  
 Установка атрибута <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> **true** вызовет вставку новой строки при нажатии клавиши ВВОД, при необходимости автоматически расширяя объект <xref:System.Windows.Controls.TextBox>, чтобы включить место для новой строки.  
  
 Атрибут <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> добавляет полосу прокрутки в <xref:System.Windows.Controls.TextBox> для просмотра содержимого <xref:System.Windows.Controls.TextBox>, если <xref:System.Windows.Controls.TextBox> превышает размеры рамки или окна, в котором он содержится.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## См. также  
 <xref:System.Windows.TextWrapping>   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)