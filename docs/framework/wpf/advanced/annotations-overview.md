---
title: "Общие сведения о заметках | Microsoft Docs"
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
  - "документы, заметки"
  - "выделение"
  - "записки"
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Общие сведения о заметках
Запись заметок или примечаний на печатных документах является таким обыденным действием, что мы воспринимаем это как само собой разумеющееся.  Эти примечания или комментарии являются «пояснениями», которые добавляются к документу для пометки информации или выделения интересующих элементов для последующего просмотра.  Хотя написание заметок на печатных документах является простым и обыденным, возможность добавлять личные примечания в электронные документы обычно очень ограничена, если вообще доступна.  
  
 В этом разделе рассматриваются обычные типы заметок, особенно клейкие заметки и световые эффекты, и рассказывается, как [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] облегчает использование этих типов заметок в приложениях при помощи элементов управления просмотра документов [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  К элементам управления просмотра документов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], поддерживающим пользовательские заметки, относятся <xref:System.Windows.Controls.FlowDocumentReader> и <xref:System.Windows.Controls.FlowDocumentScrollViewer>, а также элементы управления, унаследованные от <xref:System.Windows.Controls.Primitives.DocumentViewerBase>, как, например, <xref:System.Windows.Controls.DocumentViewer> и <xref:System.Windows.Controls.FlowDocumentPageViewer>.  
  
   
  
<a name="caf1_type_stickynotes"></a>   
## Клейкие заметки  
 Обычная клейкая заметка содержит информацию, записанную на маленьком листе цветной бумаги, который затем «приклеивается» к документу.  Цифровые клейкие заметки предоставляют похожие функциональные возможности для электронных документов, но с возможностью включения многих других типов содержимого, таких как печатный текст, рукописные заметки \(например, «рукописные» штрихи [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)]\) или веб\-ссылки.  
  
 На следующем рисунке приведены некоторые примеры выделения текста, клейких заметок и рукописных заметок.  
  
 ![Заметки с маркировкой, текстовые и прикрепленные заметки.](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF\_StickyNote")  
  
 В следующем примере показан метод, который можно использовать для включения поддержки примечаний в приложении.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## Выделение текста  
 Люди используют различные способы пометки в печатных документах для привлечения внимания к интересующим элементам, такие как подчеркивание, выделение маркером, обводка слов в предложении или рисование пометок или примечаний на полях.  Пометки выделением текста в [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] предоставляют аналогичное средство пометки информации, отображаемой в элементах управления просмотром документов в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 На следующем рисунке показан пример выделения текста.  
  
 ![Маркировка заметок](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF\_Callouts")  
  
 Пользователи обычно создают примечания, сначала выбирая некоторый текст или интересующий элемент, а затем производя нажимая правую кнопку мыши для отображения <xref:System.Windows.Controls.ContextMenu> параметров примечания.  В следующем примере показан [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], который можно использовать для объявления <xref:System.Windows.Controls.ContextMenu> с маршрутизируемыми командами, доступными пользователям для создания заметок и управления ими.  
  
 [!code-xml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## Закрепление данных  
 [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] привязывает примечания к выбранным пользователем данным, а не только к месту расположения.  Таким образом, если меняется режим отображения документа, например, когда пользователь прокручивает или изменяет размер окна отображения, примечание остается с выбранными данными, к которым оно было привязано.  Например, на следующем рисунке показана заметка, которую пользователь сделал на выделенном тексте.  При изменении отображения документа \(прокручивании, изменении размеров, масштабировании или перемещении\), заметка с помощью выделения перемещается вместе с исходным фрагментом данных.  
  
 ![Прикрепление данных заметок](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF\_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## Сопоставление заметок с аннотируемыми объектами  
 Можно сопоставить заметки с соответствующими аннотируемыми объектами.  Например, рассмотрим простое приложение для чтения документа, имеющее область примечаний.  Область примечаний может иметь вид списка, в котором отображается текст связанных с документом заметок.  Если пользователь выбирает элемент в списке, приложение отображает абзац документа, к которому привязан соответствующий объект заметки.  
  
 В следующем примере демонстрируется реализация обработчика событий такого списка, используемого в качестве области примечаний.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Другой скрипт касается приложений, позволяющих производить обмен по электронной почте примечаниями и клейкими заметками между читателями документа.  Эта возможность позволяет этим приложениям открывать страницу, содержащую присланное примечание.  
  
## См. также  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>   
 <xref:System.Windows.Controls.DocumentViewer>   
 <xref:System.Windows.Controls.FlowDocumentPageViewer>   
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>   
 <xref:System.Windows.Controls.FlowDocumentReader>   
 <xref:System.Windows.Annotations.IAnchorInfo>   
 [Схема примечаний](../../../../docs/framework/wpf/advanced/annotations-schema.md)   
 [Общие сведения о ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)   
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/ru-ru/013d68a0-5373-4a68-bd91-5de574307370)