---
title: Практическое руководство. Открытие файла, перемещенного перетаскиванием в элемент управления RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 408d48856362fa8a77a44e2cc97cb2d5ff608dcf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046356"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>Практическое руководство. Открытие файла, перемещенного перетаскиванием в элемент управления RichTextBox

В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]элементыуправления ,<xref:System.Windows.Controls.RichTextBox> и<xref:System.Windows.Documents.FlowDocument> имеют встроенную функцию перетаскивания. <xref:System.Windows.Controls.TextBox> Встроенные функции позволяют выполнять перетаскивание текста внутри элементов управления и между ними. Однако он не включает открытие файла путем перетаскивания файла на элемент управления. Эти элементы управления также помечают события перетаскивания как обработанные. В результате по умолчанию нельзя добавить собственные обработчики событий, чтобы предоставить функциональные возможности для открытия удаленных файлов.

Чтобы добавить дополнительную обработку событий перетаскивания в этих элементах управления, используйте <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> метод, чтобы добавить обработчики событий для событий перетаскивания. Задайте для `handledEventsToo` `true` параметра значение, чтобы указанный обработчик был вызван для перенаправленного события, которое уже помечено как обработанное другим элементом в маршруте события.

> [!TIP]
> Можно заменить встроенные функции <xref:System.Windows.Controls.TextBox>перетаскивания в, <xref:System.Windows.Controls.RichTextBox>и <xref:System.Windows.Documents.FlowDocument> , обрабатывая предварительные версии событий перетаскивания и пометив события предварительного просмотра как обработанные. Однако это приведет к отключению встроенных функций перетаскивания и не рекомендуется.

## <a name="example"></a>Пример

В следующем примере показано, как добавить обработчики для <xref:System.Windows.DragDrop.DragOver> событий <xref:System.Windows.DragDrop.Drop> и в <xref:System.Windows.Controls.RichTextBox>. В этом примере используется <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> метод и `handledEventsToo` задается параметр `true` , чтобы обработчики событий вызывались, несмотря на то <xref:System.Windows.Controls.RichTextBox> , что помечает эти события как обработанные. Код в обработчиках событий добавляет функции для открытия текстового файла, который удаляется из <xref:System.Windows.Controls.RichTextBox>.

Чтобы протестировать этот пример, перетащите текстовый файл или файл формата RTF из проводника <xref:System.Windows.Controls.RichTextBox>Windows в. Файл будет открыт в <xref:System.Windows.Controls.RichTextBox>. Если нажать клавишу SHIFT перед удалением файла, файл будет открыт как обычный текст.

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
