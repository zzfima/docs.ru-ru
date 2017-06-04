---
title: "Практическое руководство. Использование проверки орфографии при помощи контекстного меню | Microsoft Docs"
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
  - "включение проверки орфографии в текстовом поле [WPF]"
  - "повторное включение проверки орфографии в текстовом поле [WPF]"
  - "проверка орфографии при помощи контекстного меню [WPF]"
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Использование проверки орфографии при помощи контекстного меню
По умолчанию при включении проверки орфографии в редактируемом элементе управления, таком как <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>, варианты проверки орфографии отображаются в виде контекстного меню.  Например, когда пользователь щелкает правой кнопкой слово с ошибкой, он получают набор орфографических вариантов или вариант **Пропустить все**.  Однако при переопределении контекстного меню по умолчанию пользовательским контекстным меню эта функциональная возможность теряется и необходимо написать код для включения средства проверки орфографии в контекстном меню.  В следующем примере показано, как это можно реализовать в объекте <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 В следующем примере показан [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], создающий объект <xref:System.Windows.Controls.TextBox> с несколькими событиями, которые используются для реализации контекстного меню.  
  
 [!code-xml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## Пример  
 В следующем примере показан код, реализующий контекстное меню.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Код для элемента управления <xref:System.Windows.Controls.RichTextBox> аналогичен.  Главное различие состоит в параметре, передаваемом методу `GetSpellingError`.  Для объекта <xref:System.Windows.Controls.TextBox> передайте целочисленный индекс позиции каретки:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Для <xref:System.Windows.Controls.RichTextBox> передайте объект <xref:System.Windows.Documents.TextPointer>, задающий текущую позицию курсора:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Включение проверки орфографии в элементе управления редактирования текста](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)   
 [Использование пользовательского контекстного меню с элементом TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)