---
title: Общие сведения о RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 319dc43c0953b82da94eb6dd698f1a6afd582dbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557528"
---
# <a name="richtextbox-overview"></a>Общие сведения о RichTextBox
<xref:System.Windows.Controls.RichTextBox> Управления позволяет просмотреть или изменить содержимое потока, включая абзацев, изображения, таблицы и многое другое. В этом разделе описываются <xref:System.Windows.Controls.TextBox> класса и приводятся примеры того, как использовать его как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и C#.  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox или RichTextBox?  
 Оба <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Controls.TextBox> разрешить пользователям редактировать текст, однако используются два элемента управления в различных сценариях. Объект <xref:System.Windows.Controls.RichTextBox> является хорошим выбором при необходимости изменить форматированный текст, изображения, таблицы или других сложных элементов. Например, редактирование документа, статьи или блога, для которых требуются форматирование, изображений, и т.д., лучше всего выполнять с помощью <xref:System.Windows.Controls.RichTextBox>. Объект <xref:System.Windows.Controls.TextBox> требует меньше системных ресурсов то <xref:System.Windows.Controls.RichTextBox> и идеально подходит при только обычный текст должен быть изменен (т. е. для использования в формах). В разделе [TextBox Обзор](../../../../docs/framework/wpf/controls/textbox-overview.md) Дополнительные сведения о <xref:System.Windows.Controls.TextBox>. В таблице ниже приведены основные возможности <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox>.  
  
|Элемент управления|Проверка орфографии в режиме реального времени|Контекстное меню|Форматирование команд как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B)|<xref:System.Windows.Documents.FlowDocument> содержимого, такого как изображения, абзацы, таблицы, и т. д.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Да|Да|Нет|Нет.|  
|<xref:System.Windows.Controls.RichTextBox>|Да|Да|Да|Да|  
  
 **Примечание:** хотя <xref:System.Windows.Controls.TextBox> , не поддерживает связанные команды, такие как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B), многие основные команды поддерживаются обоими элементами управления, такие как <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Функции из приведенной выше таблицы будут подробно рассматриваться далее.  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>Создание элемента управления RichTextBox  
 В следующем примере кода показано, как создать <xref:System.Windows.Controls.RichTextBox> , пользователь может редактировать сложное содержимое.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 В частности, изменить содержимое в <xref:System.Windows.Controls.RichTextBox> является потоком содержимого. Подвижное содержимое может содержать множество типов элементов, включая форматированный текст, изображения, списки и таблицы. См. более подробные сведения о потоковых документах в разделе [Общие сведения о потоковых документах](../../../../docs/framework/wpf/advanced/flow-document-overview.md). Чтобы иметь поток содержимого <xref:System.Windows.Controls.RichTextBox> узлов <xref:System.Windows.Documents.FlowDocument> объект, который в свою очередь содержит редактируемого содержимого. Для демонстрации содержимого потока в <xref:System.Windows.Controls.RichTextBox>, ниже показано, как создать <xref:System.Windows.Controls.RichTextBox> с абзаца и текст, выделенный полужирным шрифтом.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 На рисунке ниже показано, как будет выглядеть этот пример.  
  
 ![RichTextBox с содержимым](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 Элементы, такие как <xref:System.Windows.Documents.Paragraph> и <xref:System.Windows.Documents.Bold> определить, каким образом содержимое внутри <xref:System.Windows.Controls.RichTextBox> отображается. Когда пользователи изменяют <xref:System.Windows.Controls.RichTextBox> содержимого, они изменяют содержимое потока. Дополнительные сведения о возможностях подвижного содержимого и способах работы с ним см. в разделе [Общие сведения о потоковых документах](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 **Примечание:** содержимое внутри потока <xref:System.Windows.Controls.RichTextBox> работает не так же, как и содержимого нефиксированного формата, содержащихся в других элементах управления. Например, может быть не указаны столбцы в <xref:System.Windows.Controls.RichTextBox> и поэтому не автоматического изменения размеров. Кроме того, встроенные средства как поиск, режим просмотра, навигацию по страницам и увеличение недоступны в <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>Проверка орфографии в режиме реального времени  
 Можно включить проверку правописания в реальном времени <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>. При включенной проверке орфографии все слова с ошибками подчеркиваются красной линией (см. рисунок ниже).  
  
 ![Текстовое поле с проверкой орфо&#45;графии](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Чтобы научиться включать проверку правописания, см. раздел [Включение проверки орфографии в элементе управления редактирования текста](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>Контекстное меню  
 По умолчанию оба <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> имеют контекстное меню, которое отображается при щелчке внутри элемента управления. Контекстное меню дает пользователю возможность вырезания, копирования и вставки (см. рисунок ниже).  
  
 ![TextBox с контекстным меню](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Можно создать собственное пользовательское контекстное меню, чтобы переопределить меню по умолчанию. Дополнительные сведения см. в разделе [Расположение пользовательского контекстного меню в RichTextBox](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md).  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>Команды редактирования  
 Команды редактирования позволяют пользователям форматировать редактируемое содержимое <xref:System.Windows.Controls.RichTextBox>. Помимо основных команд редактирования, <xref:System.Windows.Controls.RichTextBox> включает в себя команды форматирования, которые <xref:System.Windows.Controls.TextBox> не поддерживает. Например, при редактировании в <xref:System.Windows.Controls.RichTextBox>, пользователь может нажать CTRL + B, чтобы включить или отключить форматирование текста полужирным шрифтом. В разделе <xref:System.Windows.Documents.EditingCommands> полный список доступных команд. Помимо использования сочетания клавиш, можно подключать команды к другим элементам управления, таким как кнопки. В следующем примере показано, как создать простую панель инструментов, содержащую кнопки, с помощью которых пользователь может изменять форматирование текста.  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 На следующем рисунке показано, как будет выглядеть этот пример.  
  
 ![RichTextBox с панелью инструментов](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Определение изменения содержимого  
 Обычно <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> событие должно использоваться, чтобы определить, когда текст в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox> изменения, а затем <xref:System.Windows.UIElement.KeyDown> как можно ожидать. Пример см. в разделе [Определение изменения текста в TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>Сохранение, загрузка и печать содержимого RichTextBox  
 В следующем примере показано, как сохранить содержимое <xref:System.Windows.Controls.RichTextBox> в файл загрузки этого содержимого обратно в <xref:System.Windows.Controls.RichTextBox>и выводятся на печать содержимое. Ниже для примера приведена разметка.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 Ниже для примера приведен код.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
