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
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="ec9b4-102">Практическое руководство. Открытие файла, перетащенного в элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ec9b4-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="ec9b4-103">В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, и <xref:System.Windows.Documents.FlowDocument> все элементы управления имеют встроенные функциональные возможности перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="ec9b4-104">Встроенные функциональные возможности позволяют перетаскивания и вставки текста внутри и между элементами управления.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="ec9b4-105">Однако это не позволяет открывать файл путем перетаскивания на элементе управления.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="ec9b4-106">Эти элементы управления также пометить события перетаскивания и вставки, как обработанное.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="ec9b4-107">В результате по умолчанию нельзя добавить собственные обработчики событий для обеспечения функциональных возможностей для открытия удаленных файлов.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="ec9b4-108">Чтобы добавить дополнительную обработку событий и перетащите в этих элементах управления, используйте <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> метод, чтобы добавить обработчики событий для событий перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="ec9b4-109">Задать `handledEventsToo` параметр `true` иметь указанный обработчик вызывался для перенаправленного события, которое уже было отмечено как обработанное другим элементом на маршруте события.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ec9b4-110">Вы можете заменить встроенные функции и перетащите <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, и <xref:System.Windows.Documents.FlowDocument> , обработка версии предварительного просмотра событий и перетащите и пометив события предварительного просмотра, как обработанное.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="ec9b4-111">Тем не менее это приведет к отключению их встроенные функциональные возможности перетаскивания и вставки и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec9b4-112">Пример</span><span class="sxs-lookup"><span data-stu-id="ec9b4-112">Example</span></span>  
 <span data-ttu-id="ec9b4-113">Следующий пример демонстрирует добавление обработчиков <xref:System.Windows.DragDrop.DragOver> и <xref:System.Windows.DragDrop.Drop> событий на <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="ec9b4-114">В этом примере используется <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> метод и наборы `handledEventsToo` параметр `true` , чтобы обработчики событий будет вызываться, даже если <xref:System.Windows.Controls.RichTextBox> помечает эти события как обработанное.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="ec9b4-115">Код в обработчик событий добавляет функцию открытия текстового файла, удаляется <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="ec9b4-116">Чтобы протестировать этот пример, перетащите в текстовый файл или файл формате RTF форматированного текста из проводника Windows в <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="ec9b4-117">Файл будет открыт в <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="ec9b4-118">Если нажать клавишу SHIFT при перетаскивании файла, файл будет открыт как обычный текст.</span><span class="sxs-lookup"><span data-stu-id="ec9b4-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
