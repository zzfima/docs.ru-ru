---
title: "Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста | Microsoft Docs"
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
  - "клавиши доступа, элемент управления для"
  - "элементы управления, клавиши доступа"
  - "элементы управления, обтекание текстом"
  - "ключи, элемент управления для"
  - "обтекание текстом"
  - "обтекание текстом"
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста
В этом примере демонстрируется создание элемента управления, который имеет [клавишу доступа](GTMT) и поддерживает перенос текста.  В примере используется элемент управления <xref:System.Windows.Controls.Label> для демонстрации этих понятий.  
  
## Пример  
 **Добавление поддержки переноса текста в Label**  
  
 Элемент управления <xref:System.Windows.Controls.Label> не поддерживает перенос текста.  Если вам требуется метка, которая содержит текст в несколько строк, вы можете разместить другой элемент, который поддерживает перенос текста и поместить элемент внутри метки.  В следующем примере показано использование <xref:System.Windows.Controls.TextBlock> для создания метки, которая содержит несколько строк текста.  
  
 <!-- TODO: review snippet reference [!code-xml[Label#5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#5)]  -->
 <!-- TODO: review snippet reference [!code-xml[Label#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#5)]  -->  
  
 **Добавление клавиши доступа и поддержки переноса текста в Label**  
  
 Если вам требуется <xref:System.Windows.Controls.Label>, который имеет клавишу доступа \(назначенную\), используйте элемент <xref:System.Windows.Controls.AccessText> который расположен внутри <xref:System.Windows.Controls.Label>.  
  
 Такие элементы управления, как <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander> и <xref:System.Windows.Controls.GroupBox> имеют шаблоны элементов управления по умолчанию.  Эти шаблоны содержат <xref:System.Windows.Controls.ContentPresenter>.  Одним из свойств, которое вы можете установить в <xref:System.Windows.Controls.ContentPresenter>, является <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>\= «true», которое вы можете использовать для задания клавиши доступа для элемента управления.  
  
 Следующий пример показывает, как создать <xref:System.Windows.Controls.Label>, который имеет клавишу доступа и поддерживает перенос текста.  Чтобы включить перенос текста, пример устанавливает свойство <xref:System.Windows.Controls.AccessText.TextWrapping%2A> и используется знак подчеркивания для указания клавиши доступа.  \(Символ, который следует сразу за знаком подчеркивания, является клавишей доступа\).  
  
 <!-- TODO: review snippet reference [!code-xml[Label#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Label/XAML/Pane1.xaml#4)]  -->
 <!-- TODO: review snippet reference [!code-xml[Label#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Label/CS/Pane1.xaml#4)]  -->  
  
## См. также  
 [How to: Set the Target Property of a Label](http://msdn.microsoft.com/ru-ru/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)