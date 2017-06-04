---
title: "Практическое руководство. Определение изменения текста в TextBox | Microsoft Docs"
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
  - "обнаружение изменений в тексте"
  - "изменения в тексте, обнаружение"
  - "TextBox - элемент управления, обнаружение изменений в тексте"
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Определение изменения текста в TextBox
В этом примере показан один способ использования события <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> для выполнения метода при каждом изменении текста в элементе управления <xref:System.Windows.Controls.TextBox>.  
  
 В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащем элемент управления <xref:System.Windows.Controls.TextBox>, в котором требуется отслеживать изменения, вставьте метод, вызываемый при активации события <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>.  Этот метод должен иметь подпись, которая соответствует той, которую ожидает делегат <xref:System.Windows.Controls.TextChangedEventHandler>.  
  
 Обработчик событий вызывается для элемента управления <xref:System.Windows.Controls.TextBox> при его изменении его содержимого пользователем или программой.  
  
 **Примечание.** Данное событие вызывается при создании и первоначальном заполнении текстом элемента управления <xref:System.Windows.Controls.TextBox>.  
  
## Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], который определяет элемент управления <xref:System.Windows.Controls.TextBox>, задайте для атрибута <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> значение, соответствующее имени метода обработчика событий.  
  
 [!code-xml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## Пример  
 В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащем элемент управления <xref:System.Windows.Controls.TextBox>, в котором требуется отслеживать изменения, вставьте метод, вызываемый при активации события <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>.  Этот метод должен иметь подпись, которая соответствует той, которую ожидает делегат <xref:System.Windows.Controls.TextChangedEventHandler>.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 Обработчик событий вызывается для элемента управления <xref:System.Windows.Controls.TextBox> при его изменении его содержимого пользователем или программой.  
  
 **Примечание.** Данное событие вызывается при создании и первоначальном заполнении текстом элемента управления <xref:System.Windows.Controls.TextBox>.  
  
 Комментарии  
  
## См. также  
 <xref:System.Windows.Controls.TextChangedEventArgs>   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)