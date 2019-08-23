---
title: Общие сведения о TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 46600fd1a3023a80d49fae6f020279be6131916a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951483"
---
# <a name="textbox-overview"></a>Общие сведения о TextBox
<xref:System.Windows.Controls.TextBox> Класс позволяет отображать или редактировать неформатированный текст. Обычно используется <xref:System.Windows.Controls.TextBox> для редактирования неформатированного текста в форме. Например, форма, запрашивающая имя пользователя, номер телефона и т. д., будет <xref:System.Windows.Controls.TextBox> использовать элементы управления для ввода текста. В этом разделе описывается <xref:System.Windows.Controls.TextBox> класс и приводятся примеры его использования [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в и C#.  

<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>TextBox или RichTextBox?  
 И, <xref:System.Windows.Controls.RichTextBox> и позволяют пользователям вводить текст, но два элемента управления используются в различных сценариях. <xref:System.Windows.Controls.TextBox> Для требуется меньше системных ресурсов, <xref:System.Windows.Controls.RichTextBox> а так далее, если требуется редактировать только обычный текст (т. е. использование в форме). <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> Является лучшим выбором, когда необходимо, чтобы пользователь изменяю форматированный текст, изображения, таблицы или другое поддерживаемое содержимое. Например, изменение документа, статьи или блога, для которого требуется форматирование, изображения и т <xref:System.Windows.Controls.RichTextBox>. д., лучше всего выполнять с помощью. В следующей таблице перечислены основные возможности <xref:System.Windows.Controls.TextBox> и. <xref:System.Windows.Controls.TextBox>  
  
|Элемент управления|Проверка орфографии в режиме реального времени|Контекстное меню|Команды форматирования, <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> например (Ctrl + B)|<xref:System.Windows.Documents.FlowDocument>содержимое, например изображения, абзацы, таблицы и т. д.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Да|Да|Нет|Нет.|  
|<xref:System.Windows.Controls.RichTextBox>|Да|Да|Да (см. раздел [Общие сведения о RichTextBox](richtextbox-overview.md))|Да (см. раздел [Общие сведения о RichTextBox](richtextbox-overview.md))|  
  
> [!NOTE]
> Хотя <xref:System.Windows.Controls.TextBox> не поддерживает форматирование, связанное с правками <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> , например (Ctrl + B), многие основные команды поддерживаются обоими <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>элементами управления, такими как. Дополнительные сведения см. в разделе <xref:System.Windows.Documents.EditingCommands>.  
  
 Функции, <xref:System.Windows.Controls.TextBox> поддерживаемые в, описаны в следующих разделах. Дополнительные сведения о см <xref:System.Windows.Controls.RichTextBox>. в разделе [Общие сведения о RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Проверка орфографии в режиме реального времени  
 Проверку орфографии в режиме реального времени можно включить <xref:System.Windows.Controls.TextBox> в <xref:System.Windows.Controls.RichTextBox>или. При включенной проверке орфографии все слова с ошибками подчеркиваются красной линией (см. рисунок ниже).  
  
 ![Текстовое поле с проверкой орфо&#45;графии](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Чтобы научиться включать проверку правописания, см. раздел [Включение проверки орфографии в элементе управления редактирования текста](how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### <a name="context-menu"></a>Контекстное меню  
 По умолчанию <xref:System.Windows.Controls.TextBox> и, <xref:System.Windows.Controls.RichTextBox> и имеют контекстное меню, отображаемое, когда пользователь щелкает правой кнопкой мыши внутри элемента управления. Контекстное меню дает пользователю возможность вырезания, копирования и вставки (см. рисунок ниже).  
  
 ![TextBox с контекстным меню](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Можно создать собственное пользовательское контекстное меню, чтобы переопределить поведение по умолчанию. Дополнительные сведения см. в разделе [Использование пользовательского контекстного меню с элементом TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Создание элементов TextBox  
 <xref:System.Windows.Controls.TextBox> Может быть одной строкой по высоте или состоять из нескольких строк. Одна строка <xref:System.Windows.Controls.TextBox> лучше подходит для вывода небольших объемов обычного текста (т. е. "Имя", "Номер телефона" и т.д. в форме). В следующем примере показано, как создать одну строку <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Можно также создать <xref:System.Windows.Controls.TextBox> , который позволяет пользователю вводить несколько строк текста. Например, если ваша форма запросила биографикал наброска пользователя, необходимо использовать объект <xref:System.Windows.Controls.TextBox> , поддерживающий несколько строк текста. В следующем примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для <xref:System.Windows.Controls.TextBox> определения элемента управления, который автоматически расширяется для размещения нескольких строк текста.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Присвоение <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> `Wrap` атрибуту значения приводит к переносу текста на новую строку при достижении края элемента управления, при необходимости автоматически расширяя элемент управления, чтобы он включал в себя место для новой строки. <xref:System.Windows.Controls.TextBox.TextWrapping%2A>  
  
 Если присвоить `true` атрибуту значение, то при нажатии клавиши возврата новая строка будет вставлена, а затем автоматически <xref:System.Windows.Controls.TextBox> разворачиваться для включения в нее места для новой строки. <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>  
  
 Атрибут добавляет полосу прокрутки <xref:System.Windows.Controls.TextBox>к, что позволяет прокручивать содержимое элемента <xref:System.Windows.Controls.TextBox> , если <xref:System.Windows.Controls.TextBox> расширяется до размера фрейма или окна, в котором он находится. <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>  
  
 Дополнительные сведения о различных задачах <xref:System.Windows.Controls.TextBox>, связанных с использованием, см. [в разделах с инструкциями](textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Определение изменения содержимого  
 Обычно событие следует использовать для обнаружения изменений текста <xref:System.Windows.Controls.TextBox> в <xref:System.Windows.UIElement.KeyDown> или <xref:System.Windows.Controls.RichTextBox> , а не в том виде, в котором они могут ожидать. <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> Пример см. в разделе [Определение изменения текста в TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## <a name="see-also"></a>См. также

- [Разделы практического руководства](textbox-how-to-topics.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
