---
title: Общие сведения о TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: bb03d09b1730f4a8d607773f9024eee4f125e2c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="textbox-overview"></a>Общие сведения о TextBox
<xref:System.Windows.Controls.TextBox> Класс позволяет отображения или редактирования неформатированного текста. Обычно <xref:System.Windows.Controls.TextBox> редактирования неформатированного текста в форме. Например, форма запроса имени пользователя, номер телефона и т. д может использовать <xref:System.Windows.Controls.TextBox> элементы управления для ввода текста. В этом разделе описываются <xref:System.Windows.Controls.TextBox> класса и приводятся примеры того, как использовать его как [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и C#.  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox или RichTextBox?  
 Оба <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> позволяют пользователям вводить текст, но используются два элемента управления для различных сценариев. Объект <xref:System.Windows.Controls.TextBox> требует меньше системных ресурсов то <xref:System.Windows.Controls.RichTextBox> , это идеальный вариант, если требуется отредактировать только обычный текст (т. е. Использование в форме). Объект <xref:System.Windows.Controls.RichTextBox> является хорошим выбором при необходимости изменить форматированный текст, изображения, таблицы или другие поддерживаемые содержимого. Например, редактирование документа, статьи или блога, для которых требуются форматирование, изображений, и т.д., лучше всего выполнять с помощью <xref:System.Windows.Controls.RichTextBox>. В таблице ниже приведены основные возможности <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.TextBox>.  
  
|Элемент управления|Проверка орфографии в режиме реального времени|Контекстное меню|Форматирование команд как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B)|<xref:System.Windows.Documents.FlowDocument> содержимого, такого как изображения, абзацы, таблицы, и т. д.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Да|Да|Нет|Нет.|  
|<xref:System.Windows.Controls.RichTextBox>|Да|Да|Да (см. раздел [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|Да (см. раздел [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md))|  
  
> [!NOTE]
>  Несмотря на то что <xref:System.Windows.Controls.TextBox> выполняет команды поддерживает форматирование связанные изменения как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTRL + B), многие основные команды поддерживаются обоими элементами управления, такие как <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Дополнительные сведения см. в разделе <xref:System.Windows.Documents.EditingCommands>.  
  
 Возможности, поддерживаемые различными <xref:System.Windows.Controls.TextBox> рассматриваются в следующих разделах. Дополнительные сведения о <xref:System.Windows.Controls.RichTextBox>, в разделе [Обзор RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Проверка орфографии в режиме реального времени  
 Можно включить в режиме реального времени проверка орфографии в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>. При включенной проверке орфографии все слова с ошибками подчеркиваются красной линией (см. рисунок ниже).  
  
 ![Текстовое поле с проверкой орфо&#45;графии](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Чтобы научиться включать проверку правописания, см. раздел [Включение проверки орфографии в элементе управления редактирования текста](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Контекстное меню  
 По умолчанию оба <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> имеют контекстное меню, которое отображается при щелчке внутри элемента управления. Контекстное меню дает пользователю возможность вырезания, копирования и вставки (см. рисунок ниже).  
  
 ![TextBox с контекстным меню](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Можно создать собственное пользовательское контекстное меню, чтобы переопределить поведение по умолчанию. Дополнительные сведения см. в разделе [Использование пользовательского контекстного меню с элементом TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Создание элементов TextBox  
 Объект <xref:System.Windows.Controls.TextBox> может состоять из одной высоты или нескольких строк. Одна строка <xref:System.Windows.Controls.TextBox> лучше всего подходит для ввода небольшого объема обычного текста (т. е. "Имя", "Номер телефона" и т.д. в форме). В следующем примере демонстрируется создание одной строки <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Можно также создать <xref:System.Windows.Controls.TextBox> , позволяющий пользователю вводить несколько строк текста. Например, если форма запрашивает биографические пользователя, может потребоваться использовать <xref:System.Windows.Controls.TextBox> , поддерживающий несколько строк текста. В следующем примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемент управления, который автоматически расширяется, чтобы вместить несколько строк текста.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Установка <xref:System.Windows.Controls.TextBox.TextWrapping%2A> атрибут `Wrap` вызывает текста по словам в новую строку при краем <xref:System.Windows.Controls.TextBox> управления достигается, автоматическое расширение <xref:System.Windows.Controls.TextBox> элемента управления, чтобы включить место для новой строки, при необходимости.  
  
 Установка <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибут `true` вызывает строки должен быть вставлен при нажатии клавиши ВВОД, автоматически расширяя <xref:System.Windows.Controls.TextBox> при необходимости включите место для новой строки.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Атрибут добавляет полосу прокрутки для <xref:System.Windows.Controls.TextBox>, после чего содержимое <xref:System.Windows.Controls.TextBox> прокручивать if <xref:System.Windows.Controls.TextBox> превышает размеры фрейма или окно, в котором он содержится.  
  
 Дополнительные сведения о различных задачах, связанных с использованием <xref:System.Windows.Controls.TextBox>, в разделе [инструкции](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Определение изменения содержимого  
 Обычно <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> событие должно использоваться, чтобы определить, когда текст в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox> изменяется, а затем <xref:System.Windows.UIElement.KeyDown> как можно ожидать. Пример см. в разделе [Определение изменения текста в TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>См. также  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
