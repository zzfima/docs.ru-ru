---
title: "Практическое руководство. Получение коллекции строк из элемента TextBox | Microsoft Docs"
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
  - "линии, получение коллекции"
  - "TextBox - элемент управления, получение коллекции строк"
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Получение коллекции строк из элемента TextBox
В этом примере показано, как получить набор строк текста из элемента <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 В следующем примере используется простой метод, который принимает элемент <xref:System.Windows.Controls.TextBox> в качестве аргумента и возвращает коллекцию <xref:System.Collections.Specialized.StringCollection>, содержащую строки текста из элемента **TextBox**.  Свойство <xref:System.Windows.Controls.TextBox.LineCount%2A> используется для определения количества строк в элементе **TextBox**, а затем метод <xref:System.Windows.Controls.TextBox.GetLineText%2A> используется для извлечения каждой строки и добавления ее в коллекцию строк.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)