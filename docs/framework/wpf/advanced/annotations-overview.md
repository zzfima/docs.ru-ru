---
title: Общие сведения о заметках
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dcc881421e1a6960ab1ab9760ec2cd18a4c77c36
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="annotations-overview"></a><span data-ttu-id="78482-102">Общие сведения о заметках</span><span class="sxs-lookup"><span data-stu-id="78482-102">Annotations Overview</span></span>
<span data-ttu-id="78482-103">Добавление заметок или примечаний на печатные документы — это настолько обыденное действие, что мы воспринимаем его как должное.</span><span class="sxs-lookup"><span data-stu-id="78482-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="78482-104">Такие примечания или комментарии являются "заметками", которые мы добавляем в документ для пометки информации или выделения интересующих элементов, к которым будем обращаться в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="78482-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="78482-105">Хотя написание заметок на печатных документах является простым и обыденным, возможность добавлять личные примечания в электронные документы, как правило, очень ограниченна, если вообще доступна.</span><span class="sxs-lookup"><span data-stu-id="78482-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="78482-106">В этом разделе рассматриваются обычные типы заметок, в частности записки и выделения и показано, как [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] облегчает использование этих типов заметок в приложениях по документу Windows Presentation Foundation (WPF) элементы управления для просмотра.</span><span class="sxs-lookup"><span data-stu-id="78482-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="78482-107"> Включить просмотр документа элементы управления, которые поддерживают заметки <xref:System.Windows.Controls.FlowDocumentReader> и <xref:System.Windows.Controls.FlowDocumentScrollViewer>, а также, как элементы управления, производный от <xref:System.Windows.Controls.Primitives.DocumentViewerBase> например <xref:System.Windows.Controls.DocumentViewer> и <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span><span class="sxs-lookup"><span data-stu-id="78482-107"> document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  
  
  
<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a><span data-ttu-id="78482-108">Записки</span><span class="sxs-lookup"><span data-stu-id="78482-108">Sticky Notes</span></span>  
 <span data-ttu-id="78482-109">Обычная записка содержит информацию, написанную на маленьком листке цветной бумаги, который затем "приклеивается" к документу.</span><span class="sxs-lookup"><span data-stu-id="78482-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="78482-110">Цифровые записки предоставляют аналогичные функциональные возможности для электронных документов, однако обеспечивают дополнительную гибкость благодаря включению многих других типов содержимого, например печатного текста, рукописных заметок (например, рукописного ввода [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)]) или веб-ссылок.</span><span class="sxs-lookup"><span data-stu-id="78482-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="78482-111">Ниже показаны некоторые примеры заметок: выделение, текстовая записка и рукописная записка.</span><span class="sxs-lookup"><span data-stu-id="78482-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="78482-112">![Выделение, текстовая и рукописная записка](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="78482-112">![Highlight, text and ink sticky note annotations.](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="78482-113">В следующем примере показан метод, который можно использовать для включения поддержки заметок в приложении.</span><span class="sxs-lookup"><span data-stu-id="78482-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a><span data-ttu-id="78482-114">Выделение</span><span class="sxs-lookup"><span data-stu-id="78482-114">Highlights</span></span>  
 <span data-ttu-id="78482-115">Люди используют различные способы для привлечения внимания к интересующим элементам в бумажном документе, такие как подчеркивание, выделение, заключение слов в предложении в кружок или рисование пометок и примечаний на полях.</span><span class="sxs-lookup"><span data-stu-id="78482-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="78482-116">Заметки типа "выделение" в [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] предоставляют подобную функцию для информации, отображаемой в элементах управления для просмотра документа [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78482-116">Highlight annotations in [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] provide a similar feature for marking up information displayed in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] document viewing controls.</span></span>  
  
 <span data-ttu-id="78482-117">На следующем рисунке показан пример заметки-выделения.</span><span class="sxs-lookup"><span data-stu-id="78482-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="78482-118">![Заметка-выделение](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="78482-118">![Highlight Annotation](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="78482-119">Пользователи обычно создают примечания, сначала выберите часть текста или для рассматриваемого элемента и щелкните правой кнопкой мыши для отображения <xref:System.Windows.Controls.ContextMenu> параметров примечания.</span><span class="sxs-lookup"><span data-stu-id="78482-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="78482-120">В следующем примере показан [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] можно использовать для объявления <xref:System.Windows.Controls.ContextMenu> маршрутизируемыми командами, пользователям для создания заметок и управления ими.</span><span class="sxs-lookup"><span data-stu-id="78482-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a><span data-ttu-id="78482-121">Привязка данных</span><span class="sxs-lookup"><span data-stu-id="78482-121">Data Anchoring</span></span>  
 <span data-ttu-id="78482-122">[!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] привязывает заметки к данным, выбранным пользователем, а не только к расположению.</span><span class="sxs-lookup"><span data-stu-id="78482-122">The [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="78482-123">Таким образом, при изменении представления документа, например когда пользователь прокручивает его или изменяет размер окна отображения, заметка остается привязанной к выбранным данным.</span><span class="sxs-lookup"><span data-stu-id="78482-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="78482-124">Например, на следующем графике показана заметка, которую пользователь задал для выделенного текста.</span><span class="sxs-lookup"><span data-stu-id="78482-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="78482-125">При изменении представления документа (прокрутка, изменение размера, масштаба и т. д.) заметка-выделение перемещается вместе с исходным фрагментом данных.</span><span class="sxs-lookup"><span data-stu-id="78482-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="78482-126">![Привязка данных заметки](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="78482-126">![Annotation Data Anchoring](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="78482-127">Сопоставление заметок с объектами заметок</span><span class="sxs-lookup"><span data-stu-id="78482-127">Matching Annotations with Annotated Objects</span></span>  
 <span data-ttu-id="78482-128">Можно сопоставить заметки с соответствующими объектами заметок.</span><span class="sxs-lookup"><span data-stu-id="78482-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="78482-129">Например, рассмотрим простое приложение для чтения документа, имеющее панель комментариев.</span><span class="sxs-lookup"><span data-stu-id="78482-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="78482-130">Панель комментариев может быть полем со списком, в котором отображается текст из списка заметок, привязанных к документу.</span><span class="sxs-lookup"><span data-stu-id="78482-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="78482-131">Когда пользователь выбирает элемент в списке, приложение загружает в представление абзац в документе, к которому привязан соответствующий объект заметки.</span><span class="sxs-lookup"><span data-stu-id="78482-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="78482-132">Ниже приведен пример, демонстрирующий реализацию обработчика событий такого списка, который служит в качестве панели комментариев.</span><span class="sxs-lookup"><span data-stu-id="78482-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="78482-133">Другой сценарий касается приложений, позволяющих exchange заметок и записки между читателями документа по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="78482-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="78482-134">Эта функция позволяет таким приложениям направлять пользователя на страницу, содержащую заметку для обмена.</span><span class="sxs-lookup"><span data-stu-id="78482-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78482-135">См. также</span><span class="sxs-lookup"><span data-stu-id="78482-135">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>  
 <xref:System.Windows.Controls.DocumentViewer>  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>  
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>  
 <xref:System.Windows.Controls.FlowDocumentReader>  
 <xref:System.Windows.Annotations.IAnchorInfo>  
 [<span data-ttu-id="78482-136">Схема примечаний</span><span class="sxs-lookup"><span data-stu-id="78482-136">Annotations Schema</span></span>](../../../../docs/framework/wpf/advanced/annotations-schema.md)  
 [<span data-ttu-id="78482-137">Общие сведения об элементе ContextMenu</span><span class="sxs-lookup"><span data-stu-id="78482-137">ContextMenu Overview</span></span>](../../../../docs/framework/wpf/controls/contextmenu-overview.md)  
 [<span data-ttu-id="78482-138">Общие сведения о системе команд</span><span class="sxs-lookup"><span data-stu-id="78482-138">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="78482-139">Общие сведения о документе нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="78482-139">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="78482-140">Практическое руководство. Добавление команды в объект MenuItem</span><span class="sxs-lookup"><span data-stu-id="78482-140">How to: Add a Command to a MenuItem</span></span>](http://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)
