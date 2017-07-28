---
title: "Практическое руководство. Извлечение выделенного текста | Microsoft Docs"
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
  - "извлечение текста"
  - "текст, извлечение"
  - "TextBox - элемент управления, извлечение текста"
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Извлечение выделенного текста
В этом примере показан способ использования свойства <xref:System.Windows.Controls.TextBox.SelectedText%2A> для извлечения текста, который пользователь выделил в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 В следующем примере кода [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] демонстрируется определение элемента управления <xref:System.Windows.Controls.TextBox>, содержащего некоторый текст для выделения, и элемента управления <xref:System.Windows.Controls.Button>, для которого определен метод <xref:System.Windows.Controls.Button.OnClick%2A>.  
  
 В этом примере кнопка со связанным обработчиком событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> используется для извлечения выделения текста.  При нажатии кнопки метод <xref:System.Windows.Controls.Button.OnClick%2A> копирует любой выделенный текст в текстовом поле в строку.  В других обстоятельствах для извлечения выделенного текста \(по нажатию кнопки\), а также для других действий, выполняемых с выделенным текстом \(копирование выделенного текста в строку\), скрипт действия можно легко изменить.  
  
 [!code-xml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## Пример  
 В следующем примере [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] демонстрируется работа обработчика событий <xref:System.Windows.Controls.Button.OnClick%2A> для кнопки, определенной в коде [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для данного примера.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)