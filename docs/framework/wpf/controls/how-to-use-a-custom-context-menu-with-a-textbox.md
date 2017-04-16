---
title: "Практическое руководство. Использование пользовательского контекстного меню с элементом TextBox | Microsoft Docs"
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
  - "контекстные меню, пользовательский"
  - "настраиваемые контекстных меню"
  - "меню, пользовательский"
  - "TextBox - элемент управления, меню с настраиваемым содержимым"
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Использование пользовательского контекстного меню с элементом TextBox
В этом примере показано, как определить и реализовать простое пользовательское контекстное меню для элемента управления <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 В следующем примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] определяется элемент управления <xref:System.Windows.Controls.TextBox>, содержащий пользовательское контекстного меню.  
  
 Контекстное меню определено с помощью элемента <xref:System.Windows.Controls.ContextMenu>.  Само контекстное меню состоит из последовательности элементов <xref:System.Windows.Controls.MenuItem> и <xref:System.Windows.Controls.Separator>.  Каждый элемент <xref:System.Windows.Controls.MenuItem> определяет команду в контекстном меню, атрибут <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> определяет отображаемый текст для команды меню, а атрибут <xref:System.Windows.Controls.MenuItem.Click> указывает метод обработчика для каждого элемента меню.  Элемент <xref:System.Windows.Controls.Separator> просто отображает разделяющую строку между предыдущим и последующим элементами меню.  
  
 [!code-xml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## Пример  
 В следующем примере показан код реализации предыдущего определения контекстного меню, а также код, который включает и отключает контекстное меню.  Событие <xref:System.Windows.Controls.ContextMenu.Opened> используется для динамического включения или отключения определенных команд в зависимости от текущего состояния элемента управления <xref:System.Windows.Controls.TextBox>.  
  
 Чтобы восстановить контекстное меню по умолчанию, используйте метод <xref:System.Windows.DependencyObject.ClearValue%2A> для очистки значения свойства <xref:System.Windows.FrameworkElement.ContextMenu%2A>.  Чтобы полностью отключить контекстное меню, задайте для свойства <xref:System.Windows.FrameworkElement.ContextMenu%2A> пустую ссылку \(`Nothing` в Visual Basic\).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## См. также  
 [Использование проверки орфографии при помощи контекстного меню](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)