---
title: "Общие сведения о TextBox | Microsoft Docs"
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
  - "элементы управления, TextBox"
  - "TextBox - элемент управления, сведения об элементе управления TextBox"
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения о TextBox
Класс <xref:System.Windows.Controls.TextBox> позволяет отобразить или отредактировать неформатированный текст.  Часто <xref:System.Windows.Controls.TextBox> используется для изменения неформатированного текста в форме.  Например, форма запроса имени пользователя, номера телефона и т.д может использовать для ввода текста элемент управления <xref:System.Windows.Controls.TextBox>.  В этом разделе представляется класс <xref:System.Windows.Controls.TextBox> и приводятся примеры его использования в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)].  
  
   
  
<a name="textbox_or_richtextbox"></a>   
## Textbox или RichTextBox?  
 Элементы управления <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> позволяют пользователям вводить текст, но они используются для различных скриптов.  Для <xref:System.Windows.Controls.TextBox> требуется меньших системных затрат, чем для <xref:System.Windows.Controls.RichTextBox>, поэтому он идеально подходит, если требуется отредактировать только обычный текст \(использование в форме\).  <xref:System.Windows.Controls.RichTextBox> является хорошим выбором при необходимости изменить форматированный текст, рисунки, таблицы или другие поддерживаемые типы содержимого.  Например, редактирование документа, статьи или блога, для которых требуются форматирование, рисунки и т.д., лучше всего выполнять с помощью <xref:System.Windows.Controls.RichTextBox>.  В нижеприведенной таблице перечислены основные возможности <xref:System.Windows.Controls.TextBox>и <xref:System.Windows.Controls.TextBox>.  
  
|Элемент управления|Проверка орфографии в режиме реального времени|Контекстное меню|Форматирование команд как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(CTRL \+ B\)|Содержимое <xref:System.Windows.Documents.FlowDocument>, такое как изображения, абзацы, таблицы и т.д.|  
|------------------------|----------------------------------------------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Да|Да|Нет|Нет.|  
|<xref:System.Windows.Controls.RichTextBox>|Да|Да|Да \(см. [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)\)|Да \(см. [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)\)|  
  
> [!NOTE]
>  Хотя <xref:System.Windows.Controls.TextBox> не поддерживает форматирование, связанное с командами редактирования, такими как <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(Ctr \+ B\), многие основные команды поддерживаются обоими элементами управления, например <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  Дополнительные сведения см. в разделе <xref:System.Windows.Documents.EditingCommands>.  
  
 Функции, поддерживаемые элементом <xref:System.Windows.Controls.TextBox>, рассматриваются в следующих разделах.  Дополнительные сведения о <xref:System.Windows.Controls.RichTextBox> см. в разделе [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### Проверка орфографии в режиме реального времени  
 В <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.RichTextBox> можно запустить проверку орфографии в режиме реального времени.  При включенной проверке орфографии все неправильно написанные слова подчеркиваются красной линией \(см. рисунок\).  
  
 ![Textbox с проверкой правописания](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 Сведения о том, как включить проверку орфографии, см. в разделе [Включение проверки орфографии в элементе управления редактирования текста](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md).  
  
### Контекстное меню  
 По умолчанию и <xref:System.Windows.Controls.TextBox>, и <xref:System.Windows.Controls.RichTextBox> имеют контекстное меню, которое появляется при щелчке правой кнопкой мыши внутри элемента управления.  Контекстное меню предоставляет пользователю возможность вырезания, копирования или вставки \(см. рисунок\).  
  
 ![TextBox с контекстным меню](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 Можно создать собственное контекстное меню, чтобы переопределить поведение по умолчанию.  Дополнительные сведения см. в разделе [Использование пользовательского контекстного меню с элементом TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md).  
  
<a name="creating_textboxes"></a>   
## Создание элемента TextBox  
 Элемент <xref:System.Windows.Controls.TextBox> может состоять из одной или нескольких строк.  Однострочный <xref:System.Windows.Controls.TextBox> лучше всего подходит для ввода небольшого объема обычного текста \(такого как  "Имя", "Номер телефона" и т. д.  в форме\).  В следующем примере показано, как создать однострочный <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 Также можно создать <xref:System.Windows.Controls.TextBox>, позволяющий пользователю вводить несколько строк текста.  Например, если форма запрашивает биографические сведения о пользователе, следует использовать <xref:System.Windows.Controls.TextBox>, поддерживающий несколько строк текста.  В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения элемента управления <xref:System.Windows.Controls.TextBox>, который будет автоматически расширяться, чтобы вместить несколько строк текста.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Установка для атрибута <xref:System.Windows.Controls.TextBox.TextWrapping%2A> значения `Wrap` вызовет перенос вводимого текста на новую строку при достижении края элемента управления <xref:System.Windows.Controls.TextBox>, при необходимости автоматически расширяя элемент управления <xref:System.Windows.Controls.TextBox>, чтобы он включал место для новой строки.  
  
 Установка атрибута <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> в значение `true` вызовет вставку новой строки при нажатии клавиши RETURN, при необходимости автоматически расширяя <xref:System.Windows.Controls.TextBox>, чтобы он включал место для новой строки.  
  
 Атрибут <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> добавляет полосу прокрутки в <xref:System.Windows.Controls.TextBox> для просмотра содержимого <xref:System.Windows.Controls.TextBox>, если <xref:System.Windows.Controls.TextBox> превышает размеры рамки или окна, в котором он содержится.  
  
 Дополнительные сведения о различных задачах, связанных с использованием <xref:System.Windows.Controls.TextBox>, см. в разделе [Практические руководства](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## Определение изменения содержимого  
 Обычно для обнаружения изменения текста в <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox> следует использовать событие <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>, а не <xref:System.Windows.UIElement.KeyDown>, как можно предположить.  Пример см. в разделе [Определение изменения текста в TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md).  
  
## См. также  
 [Практические руководства](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)   
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)