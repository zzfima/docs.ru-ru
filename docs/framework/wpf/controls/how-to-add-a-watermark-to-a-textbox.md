---
title: "Практическое руководство. Добавление предела в элемент TextBox | Microsoft Docs"
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
  - "расширение полезности элемента TextBox с помощью фонового изображения [WPF]"
  - "отображение фонового изображения в текстовом поле для упрощения пользовательского ввода [WPF]"
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Добавление предела в элемент TextBox
В следующем примере показано, как поддержать полезность элемента <xref:System.Windows.Controls.TextBox> с помощью отображения пояснительного фонового изображение внутри данного <xref:System.Windows.Controls.TextBox> до введения текста пользователем \(после чего изображения удаляется\).  Кроме того, фоновое изображение восстанавливается, если пользователь удаляет входные данные.  См. рисунок ниже.  
  
 ![TextBox с фоновым изображением](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing\_TextBox\_using\_background\_image")  
  
> [!NOTE]
>  Основание для использования в этом примере фонового рисунка вместо применения свойства <xref:System.Windows.Controls.TextBox.Text%2A> элемента управления <xref:System.Windows.Controls.TextBox> заключается в том, что фоновый рисунок не будет конфликтовать со связыванием данных.  
  
## Пример  
 [!code-xml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)