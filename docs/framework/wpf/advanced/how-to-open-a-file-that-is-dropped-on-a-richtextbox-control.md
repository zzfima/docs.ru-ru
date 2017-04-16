---
title: "Практическое руководство. Открытие файла, перетащенного в элемент управления RichTextBox | Microsoft Docs"
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
  - "перетаскивание [WPF], открытие перенесенного файла"
  - "перетаскивание [WPF], RichTextBox"
  - "RichTextBox [WPF], перетаскивание"
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Открытие файла, перетащенного в элемент управления RichTextBox
В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементы управления <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Documents.FlowDocument> поддерживают встроенные функции перетаскивания.  С помощью этих встроенных функций можно перетаскивать текст внутри элементов управления и между ними.  Однако они не позволяют открывать файл путем его перетаскивания на элемент управления.  Эти элементы управления также помечают события перетаскивания как обработанные.  В результате, по умолчанию нельзя добавить собственные обработчики событий для поддержки открывания перетащенных файлов.  
  
 Чтобы добавить дополнительную обработку событий перетаскивания в элементы управления, необходимо использовать метод <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> для добавления пользовательских обработчиков событий перетаскивания.  Чтобы вызвать указанный обработчик для перенаправленного события, которое уже помечено как обработанное другим элементом, расположенным в маршруте события, задайте параметру `handledEventsToo` значение `true`.  
  
> [!TIP]
>  Встроенные функции перетаскивания элементов управления <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Documents.FlowDocument> можно заменить, обработав версии предварительного просмотра событий перетаскивания и пометив события предварительного просмотра как обработанные.  Однако применение этого способа не рекомендуется, поскольку он приводит к отключению встроенных функций перетаскивания.  
  
## Пример  
 В следующем примере демонстрируется добавление обработчиков событий <xref:System.Windows.DragDrop.DragOver> и <xref:System.Windows.DragDrop.Drop> для элемента управления <xref:System.Windows.Controls.RichTextBox>.  В этом примере используется метод <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> и задается значение `true` для параметра `handledEventsToo`, поэтому обработчики событий будут вызываться, даже если элемент управления <xref:System.Windows.Controls.RichTextBox> помечает эти события как обработанные.  Код обработчиков событий добавляет функцию открытия текстового файла при его перетаскивании на элемент управления <xref:System.Windows.Controls.RichTextBox>.  
  
 Для проверки работы примера перетащите текстовый или RTF\-файл из проводника на элемент управления <xref:System.Windows.Controls.RichTextBox>.  Файл будет открыт в элементе управления <xref:System.Windows.Controls.RichTextBox>.  Если при перетаскивании файла удерживать клавишу SHIFT, файл будет открыт как обычный текст.  
  
 [!code-xml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]