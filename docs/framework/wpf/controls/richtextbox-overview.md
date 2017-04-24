---
title: "Общие сведения о RichTextBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления, RichTextBox"
  - "RichTextBox - элемент управления [WPF], об элементе управления RichTextBox"
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Общие сведения о RichTextBox
Элемент управления <xref:System.Windows.Controls.RichTextBox> позволяет отображать или изменять содержимое потока, в том числе абзацы, изображения, таблицы и др.  В этом разделе представляется класс <xref:System.Windows.Controls.TextBox> и приводятся примеры его использования в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)].  
  
   
  
<a name="textbox_or_richtextbox"></a>   
## Textbox или RichTextBox?  
 И <xref:System.Windows.Controls.RichTextBox>, и <xref:System.Windows.Controls.TextBox> позволяют пользователям редактировать текст, однако эти два элемента управления используются в различных скриптах.  <xref:System.Windows.Controls.RichTextBox> является хорошим выбором при необходимости изменить форматированный текст, рисунки, таблицы или другие сложные элементы.  Например, редактирование документа, статьи или блога, для которых требуются форматирование, рисунки и т.д., лучше всего выполнять с помощью <xref:System.Windows.Controls.RichTextBox>.  Объект <xref:System.Windows.Controls.TextBox> требует меньшего количества системных ресурсов, чем <xref:System.Windows.Controls.RichTextBox>, и идеально подходит, когда требуется отредактировать только обычный текст \(другими словами,  для использования в формах\).  Дополнительные сведения по [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md) см. в разделе <xref:System.Windows.Controls.TextBox>.  В приводимой далее таблице перечислены основные возможности <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox>.  
  
|Элемент управления|Проверка орфографии в режиме реального времени|Контекстное меню|Форматирование команд как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(CTRL \+ B\)|Содержимое <xref:System.Windows.Documents.FlowDocument>, такое как изображения, абзацы, таблицы и т.д.|  
|------------------------|----------------------------------------------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Да|Да|Нет|Нет.|  
|<xref:System.Windows.Controls.RichTextBox>|Да|Да|Да|Да|  
  
 **Примечание.** Хотя <xref:System.Windows.Controls.TextBox> не поддерживает команды, связанные с форматированием, такие как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(CTRL\+B\), многие основные команды поддерживаются обоими элементами управления, например <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Средства из приведенной выше таблицы будут рассмотрены дальше более подробно.  
  
<a name="creating_a_richtextbox"></a>   
## Создание RichTextBox  
 В следующем примере кода демонстрируется создание <xref:System.Windows.Controls.RichTextBox>, в котором пользователь может редактировать сложное содержимое.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 В частности, содержимое, редактируемое в <xref:System.Windows.Controls.RichTextBox>, является потоком содержимого.  Поток содержимого может содержать множество типов элементов, включая форматированный текст, изображения, списки и таблицы.  Более подробная информация о документах потока содержится в разделе [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  Чтобы иметь поток содержимого, <xref:System.Windows.Controls.RichTextBox> помещает объект <xref:System.Windows.Documents.FlowDocument>, который, в свою очередь, в которой находится изменяемое содержимое.  Для демонстрации содержимого потока в <xref:System.Windows.Controls.RichTextBox>, следующий фрагмент кода иллюстрирует создание <xref:System.Windows.Controls.RichTextBox> с абзацем и полужирным текстом.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 На следующем рисунке показано, как будет выглядеть этот пример.  
  
 ![RichTextBox с содержимым](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing\_RichTextBox\_with\_Content")  
  
 Элементы, такие как <xref:System.Windows.Documents.Paragraph> и <xref:System.Windows.Documents.Bold>, определяют, как появляется содержимое внутри <xref:System.Windows.Controls.RichTextBox>.  Когда пользователи изменяют содержимое <xref:System.Windows.Controls.RichTextBox>, они изменяют содержимое потока.  Дополнительные возможности потока содержимого и способы работы с ним описываются в разделе [Общие сведения о документе нефиксированного формата](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 **Примечание** Содержимое потока внутри <xref:System.Windows.Controls.RichTextBox> ведет себя не так, как содержимое потока, имеющееся в других элементах управления.  Например, в <xref:System.Windows.Controls.RichTextBox> нет столбцов и, следовательно, нет автоматического изменения размеров.  Кроме того, такие встроенные средства как поиск, режим просмотра, навигация по странице и масштабирование недоступны в <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="realtime_spellechecking"></a>   
## Проверка орфографии в режиме реального времени.  
 В <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> можно запустить проверку орфографии в режиме реального времени.  При включенной проверке орфографии все неправильно написанные слова подчеркиваются красной линией \(см. рисунок\).  
  
 ![Textbox с проверкой правописания](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 Сведения о том, как включить проверку орфографии, см. в разделе [Включение проверки орфографии в элементе управления редактирования текста](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
<a name="context_menu"></a>   
## Контекстное меню  
 По умолчанию и <xref:System.Windows.Controls.TextBox>, и <xref:System.Windows.Controls.RichTextBox> имеют контекстное меню, которое появляется при щелчке правой кнопкой мыши внутри элемента управления.  Контекстное меню предоставляет пользователю функции вырезания, копирования или вставки \(см. рисунок ниже\).  
  
 ![TextBox с контекстным меню](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 Можно создать собственное пользовательское контекстное меню, переопределив тем самым контекстное меню по умолчанию.  Дополнительные сведения см. в разделе [Расположение пользовательского контекстного меню в RichTextBox](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md).  
  
<a name="detect_when_content_changes"></a>   
## Команды редактирования  
 Команды редактирования позволяют пользователям форматировать редактируемое содержимое в <xref:System.Windows.Controls.RichTextBox>.  Помимо основных команд редактирования, <xref:System.Windows.Controls.RichTextBox> включает команды форматирования, которые <xref:System.Windows.Controls.TextBox> не поддерживает.  Например, при редактировании в <xref:System.Windows.Controls.RichTextBox>, пользователь может переключать форматирование текста полужирным шрифтом, нажав комбинацию клавиш CTRL\+B.  Полный список доступных команд можно посмотреть в разделе <xref:System.Windows.Documents.EditingCommands>.  В дополнение к использованию сочетания клавиш, можно подключать команды к другим элементам управления, таким как кнопки.  В следующем примере показано, как создать простую панель инструментов, содержащую кнопки, с помощью которых пользователь может изменять форматирование текста.  
  
 [!code-xml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 На следующем рисунке показано, как будет выглядеть этот пример.  
  
 ![RichTextBox с панелью инструментов](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.png "Editing\_RichTextBox\_with\_TooBar")  
  
<a name="editing_commands"></a>   
## Определение момента изменения содержимого  
 Чтобы определить, когда изменяется текст в элементе <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>, обычно используется событие <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>, а не <xref:System.Windows.UIElement.KeyDown>, как можно было бы предположить.  Пример см. в разделе [Определение изменения текста в TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## Сохранение, загрузка и печать содержимого RichTextBox  
 В следующем примере демонстрируется сохранение содержимого <xref:System.Windows.Controls.RichTextBox> в файл, загрузка этого содержимого обратно в <xref:System.Windows.Controls.RichTextBox> и печать содержимого.  Ниже в примере приведен код разметки.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 Ниже приведен полный код.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## См. также  
 [Практические руководства](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)   
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)