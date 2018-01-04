---
title: "Практическое руководство. Открытие файла, перетащенного в элемент управления RichTextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dfb5f0f442b18159c18a6e5345f6757674fbb90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Практическое руководство. Открытие файла, перетащенного в элемент управления RichTextBox
В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, и <xref:System.Windows.Documents.FlowDocument> все элементы управления имеют встроенные функциональные возможности перетаскивания и вставки. Встроенные функциональные возможности позволяют перетаскивания и вставки текста внутри и между элементами управления. Однако это не позволяет открывать файл путем перетаскивания на элементе управления. Эти элементы управления также пометить события перетаскивания и вставки, как обработанное. В результате по умолчанию нельзя добавить собственные обработчики событий для обеспечения функциональных возможностей для открытия удаленных файлов.  
  
 Чтобы добавить дополнительную обработку событий и перетащите в этих элементах управления, используйте <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> метод, чтобы добавить обработчики событий для событий перетаскивания и вставки. Задать `handledEventsToo` параметр `true` иметь указанный обработчик вызывался для перенаправленного события, которое уже было отмечено как обработанное другим элементом на маршруте события.  
  
> [!TIP]
>  Вы можете заменить встроенные функции и перетащите <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, и <xref:System.Windows.Documents.FlowDocument> , обработка версии предварительного просмотра событий и перетащите и пометив события предварительного просмотра, как обработанное. Тем не менее это приведет к отключению их встроенные функциональные возможности перетаскивания и вставки и не рекомендуется.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует добавление обработчиков <xref:System.Windows.DragDrop.DragOver> и <xref:System.Windows.DragDrop.Drop> событий на <xref:System.Windows.Controls.RichTextBox>. В этом примере используется <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> метод и наборы `handledEventsToo` параметр `true` , чтобы обработчики событий будет вызываться, даже если <xref:System.Windows.Controls.RichTextBox> помечает эти события как обработанное. Код в обработчик событий добавляет функцию открытия текстового файла, удаляется <xref:System.Windows.Controls.RichTextBox>.  
  
 Чтобы протестировать этот пример, перетащите в текстовый файл или файл формате RTF форматированного текста из проводника Windows в <xref:System.Windows.Controls.RichTextBox>. Файл будет открыт в <xref:System.Windows.Controls.RichTextBox>. Если нажать клавишу SHIFT при перетаскивании файла, файл будет открыт как обычный текст.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
