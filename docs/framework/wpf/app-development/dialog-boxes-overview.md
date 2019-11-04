---
title: Общие сведения о диалоговых окнах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: 9ec6716fefdc8de75d7e523c56ae0b3a02c8cf02
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424647"
---
# <a name="dialog-boxes-overview"></a>Общие сведения о диалоговых окнах
Изолированные приложения обычно имеют главное окно, в котором отображаются основные данные, по которым работает приложение, и обеспечивается возможность обработки этих данных с помощью механизмов [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], таких как строки меню, панели инструментов и строки состояния. Нетривиальное приложение может также отображать дополнительные окна для следующих целей:  
  
- отображения определенных сведений для пользователей;  
  
- сбора сведений от пользователей;  
  
- сбора и отображения сведений.  
  
 Эти типы окон называются *диалоговыми окнами*, и существует два типа: модальные и немодальные.  
  
 *Модальное* диалоговое окно отображается функцией, когда для продолжения работы функции требуются дополнительные данные от пользователя. Поскольку функция зависит от модального диалогового окна для сбора данных, это окно также не разрешает пользователю активизировать другие окна в приложении, пока остается открытым. В большинстве случаев модальное диалоговое окно позволяет пользователю подать сигнал о завершении работы с модальным диалоговым окном, нажав кнопку **ОК** или **Отмена** . Нажатие кнопки **ОК** означает, что пользователь вводит данные и желает, чтобы функция продолжала обрабатывать эти данные. Нажатие кнопки **Отмена** означает, что пользователь хочет остановить выполнение функции. Наиболее распространенными примерами модальных диалоговых окон являются окна, которые отображаются для открытия, сохранения и печати данных.  
  
 *Немодальное* диалоговое окно, с другой стороны, не мешает пользователю активировать другие окна, пока оно открыто. Например, если пользователь хочет найти вхождения конкретного слова в документе, главное окно часто открывает диалоговое окно с запросом слова для поиска. Так как поиск слова не мешает пользователю редактировать документ, диалоговое окно не обязательно должно быть модальным. Немодальное диалоговое окно, по крайней мере, содержит кнопку **Закрыть** для закрытия диалогового окна и может предоставлять дополнительные кнопки для выполнения конкретных функций, таких как кнопка **Найти далее** , чтобы найти следующее слово, совпадающее с критерием поиска слова.  
  
 Windows Presentation Foundation (WPF) позволяет создавать несколько типов диалоговых окон, включая окна сообщений, общие диалоговые окна и пользовательские диалоговые окна. В этом разделе обсуждаются все, а в [образце диалогового окна](https://go.microsoft.com/fwlink/?LinkID=159984) приведены соответствующие примеры.  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Окна сообщений  
 Окно *сообщения* является диалоговым, которое можно использовать для вывода текстовой информации и разрешения пользователям принимать решения с помощью кнопок. На следующем рисунке показано окно сообщения, в котором отображается текстовая информация, задается вопрос и предоставляются три кнопки для ответа на этот вопрос.  
  
 ![Диалоговое окно «текстовый процессор» с вопросом, нужно ли сохранить изменения в документе перед закрытием приложения.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Чтобы создать окно сообщения, используйте класс <xref:System.Windows.MessageBox>. <xref:System.Windows.MessageBox> позволяет настроить текст, заголовок, значок и кнопки в окне сообщения, используя код, подобный приведенному ниже.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Чтобы отобразить окно сообщения, вызовите метод `static`<xref:System.Windows.MessageBox.Show%2A>, как показано в следующем коде.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Когда коду, который показывает окно сообщения, нужно определить и обработать решение пользователя (какая кнопка была нажата), он может проверить результат окна сообщения, как показано в следующем коде.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Дополнительные сведения об использовании окон сообщений см. в разделе <xref:System.Windows.MessageBox>, [MessageBox Sample](https://go.microsoft.com/fwlink/?LinkID=160023)и [Образец диалогового окна](https://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Хотя <xref:System.Windows.MessageBox> может предоставлять простое взаимодействие с пользователем в диалоговом окне, преимущество использования <xref:System.Windows.MessageBox> заключается в том, что это единственный тип окна, которое может быть отображено приложениями, выполняемыми в песочнице безопасности с частичным доверием (см. раздел [Безопасность](../security-wpf.md)), например в браузере XAML. приложения (XBAP).  
  
 Большинство диалоговых окон отображают и собирают более сложные данные, чем результат окна сообщения, в том числе текст, выбранные варианты (флажки), взаимоисключающий выбор (переключатели) и списки выбора (списки, поля со списком, поля с раскрывающимся списком). Для этого Windows Presentation Foundation (WPF) предоставляет несколько общих диалоговых окон и позволяет создавать собственные диалоговые окна, хотя использование либо ограничено приложениями, работающими с полным доверием.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Общие диалоговые окна  
 В Windows реализовано множество многократно используемых диалоговых окон, которые являются общими для всех приложений, включая диалоговые окна для открытия файлов, сохранения файлов и печати. Поскольку эти диалоговые окна реализованы операционной системой, они могут совместно использоваться всеми приложениями, работающими в операционной системе, что помогает поддерживать единообразие пользовательского интерфейса; если пользователи знакомы с диалоговым окном, предоставляемым операционной системой в одном приложении, им не нужно учиться пользоваться этим диалоговым окном в других приложениях. Поскольку эти диалоговые окна доступны для всех приложений, и они помогают обеспечить единообразное взаимодействие с пользователем, они называются *общими диалоговыми окнами*.  
  
 Windows Presentation Foundation (WPF) инкапсулирует общие диалоговые окна открытия файла, сохранения файлов и печати и предоставляет их в качестве управляемых классов для использования в автономных приложениях. В этом разделе приводится краткий обзор каждого типа диалоговых окон.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Диалоговое окно открытия файла  
 Диалоговое окно открытия файлов, показанное на следующем рисунке, используется функциональностью открытия файла для получения имени открываемого файла.  
  
 ![Открытие диалогового окна, показывающего расположение для извлечения файла.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 Общее диалоговое окно открытия файла реализуется как класс <xref:Microsoft.Win32.OpenFileDialog> и находится в пространстве имен <xref:Microsoft.Win32>. Следующий код показывает, как создавать, настраивать и отображать такое окно, а также как обрабатывать результат.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Дополнительные сведения о диалоговом окне Открытие файла см. в разделе <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog> можно использовать для безопасного извлечения имен файлов приложениями, работающими с частичным доверием (см. раздел [Безопасность](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>диалоговое окно сохранения файлов  
 Диалоговое окно сохранения файлов, показанное на следующем рисунке, используется функциональностью сохранения файла для получения имени сохраняемого файла.  
  
 ![Диалоговое окно Сохранить как, в котором отображается расположение для сохранения файла.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Диалоговое окно "общий файл сохранения" реализуется как класс <xref:Microsoft.Win32.SaveFileDialog> и находится в пространстве имен <xref:Microsoft.Win32>. Следующий код показывает, как создавать, настраивать и отображать такое окно, а также как обрабатывать результат.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Дополнительные сведения о диалоговом окне "Сохранение файла" см. в разделе <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Печать - диалоговое окно

Диалоговое окно печати, показанное на следующем рисунке, используется функциональными возможностями печати для выбора и настройки принтера, на котором пользователь хочет печатать данные.  
  
![Снимок экрана, на котором показано диалоговое окно "Печать".](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
Общее диалоговое окно печати реализуется как класс <xref:System.Windows.Controls.PrintDialog> и находится в пространстве имен <xref:System.Windows.Controls>. Следующий код показывает, как создавать, настраивать и отображать такое окно.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Дополнительные сведения о диалоговом окне Печать см. в разделе <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>. Подробное описание печати в WPF см. в разделе [Общие сведения о печати](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Настраиваемые диалоговые окна

Хотя общие диалоговые окна полезны и должны использоваться, когда это возможно, они не поддерживают требований диалоговых окон отдельного домена. В этих случаях необходимо создавать собственные диалоговые окна. Как мы увидим, диалоговое окно является окном со специальным поведением. <xref:System.Windows.Window> реализует эти поведения и, следовательно, для создания настраиваемых модальных и немодальных диалоговых окон используется <xref:System.Windows.Window>.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Создание модального настраиваемого диалогового окна

В этом разделе показано, как использовать <xref:System.Windows.Window> для создания типичной реализации модального диалогового окна, используя диалоговое окно `Margins` в качестве примера (см. [Пример диалогового окна](https://go.microsoft.com/fwlink/?LinkID=159984)). На следующем рисунке показано диалоговое окно `Margins`.  
  
 ![Диалоговое окно «поля» с полями для определения левого поля, верхнего поля, правого поля и нижнего поля.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Настройка модального диалогового окна

Пользовательский интерфейс для типичного диалогового окна включает следующее.  
  
- Различные элементы управления, которые необходимы для сбора нужных данных.  
  
- Кнопка **ОК** , которую пользователь нажимаем, чтобы закрыть диалоговое окно, вернуться к функции и продолжить обработку.  
  
- Кнопка **"Отмена"** , которую пользователь нажмет для закрытия диалогового окна и прекращения дальнейшей обработки функции.  
  
- Кнопка **Закрыть** в заголовке окна.  
  
- Значок.  
  
- Кнопки **сворачивания**, **развертывания**и **восстановления** .  
  
- **Системное** меню для сворачивания, развертывания, восстановления и закрытия диалогового окна.  
  
- Расположение выше и в центре окна, открывшего диалоговое окно.  
  
- Возможность изменять размер, если это возможно, чтобы не допустить слишком маленького диалогового окна, а также предоставить пользователю полезный размер по умолчанию. Для этого необходимо задать значения по умолчанию и минимальные размеры.  
  
- Клавиша ESC в качестве сочетания клавиш, которое вызывает нажатие кнопки **Отмена** . Это можно сделать, задав для свойства <xref:System.Windows.Controls.Button.IsCancel%2A> кнопки **Отмена** значение `true`.  
  
- Клавиша ВВОД (или возврата) в качестве сочетания клавиш, которое вызывает нажатие кнопки **ОК** . Для этого нужно задать свойство <xref:System.Windows.Controls.Button.IsDefault%2A> кнопки **ок** `true`.  
  
Следующий код демонстрирует такую конфигурацию.  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
Пользовательский интерфейс для диалогового окна также распространяется в строку меню окна, открывающего диалоговое окно. Если пункт меню вызывает функцию, которая перед продолжением выполнения требует взаимодействия с пользователем посредством диалогового окна, то в названии этого пункта меню будет многоточие в заголовке, как показано ниже.  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
Если пункт меню вызывает функцию, которая отображает диалоговое окно, не требующее взаимодействия с пользователем, например диалоговое окно "О программе", многоточие не требуется.  
  
#### <a name="opening-a-modal-dialog-box"></a>Открытие модального диалогового окна

Диалоговое окно обычно отображается в результате выбора пользователем пункта меню для выполнения доменной функции, такой как установка полей документа в текстовом процессоре. Отображение диалогового окна похоже на отображение обычного окна, хотя требуется дополнительная настройка для диалогового окна. Весь процесс создания, настройки и открытия диалогового окна показан в следующем коде.  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

Здесь код передает в диалоговое окно сведения по умолчанию (текущие поля). В нем также задается свойство <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> со ссылкой на окно, в котором отображается диалоговое окно. В общем случае необходимо всегда задавать владельца для диалогового окна, чтобы обеспечить поведение окна, которое является общим для всех диалоговых окон (Дополнительные сведения см. в разделе [Обзор Windows WPF](wpf-windows-overview.md) ).

> [!NOTE]
> Необходимо указать владельца для поддержки автоматизации ПОЛЬЗОВАТЕЛЬСКОГО интерфейса для диалоговых окон (см. [Обзор модели автоматизации пользовательского](../../ui-automation/ui-automation-overview.md)интерфейса).

После настройки диалогового окна он отображается как модальный путем вызова метода <xref:System.Windows.Window.ShowDialog%2A>.  
  
#### <a name="validating-user-provided-data"></a>Проверка предоставленных пользователем данных

Если открывается диалоговое окно и пользователь предоставляет требуемые данные, диалоговое окно отвечает за проверку допустимости предоставленных данных по следующим причинам.  
  
- С точки зрения безопасности следует проверять все входные данные.  
  
- С точки зрения конкретного домена проверка данных предотвращает обработку в коде ошибочных данных, которые могут вызывать исключения.  
  
- С точки зрения взаимодействия с пользователем диалоговое окно может помочь пользователям, показывая, какие введенные ими данные являются недопустимыми.  
  
- С точки зрения производительности проверка данных в многоуровневом приложении может уменьшить количество циклов обработки между уровнями клиента и приложения, особенно в том случае, если в приложение входят веб-службы или серверные базы данных.  

Чтобы проверить привязанный элемент управления в WPF, необходимо определить правило проверки и связать его с привязкой. Правило проверки — это пользовательский класс, производный от <xref:System.Windows.Controls.ValidationRule>. В следующем примере показано правило проверки `MarginValidationRule`, которое проверяет, что привязанное значение является <xref:System.Double> и находится в пределах указанного диапазона.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

В этом коде логика проверки правила проверки реализуется путем переопределения метода <xref:System.Windows.Controls.ValidationRule.Validate%2A>, который проверяет данные и возвращает соответствующие <xref:System.Windows.Controls.ValidationResult>.  

Чтобы сопоставить это правило проверки со связанным элементом управления, используется следующая разметка.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

После того как правило проверки будет связано, WPF автоматически применит его при входе данных в привязанный элемент управления. Если элемент управления содержит недопустимые данные, WPF отобразит красную рамку вокруг недопустимого элемента управления, как показано на следующем рисунке.  
  
![Диалоговое окно полей с красной границей вокруг недействительного значения левого поля.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF не ограничивает доступ пользователя к недопустимому элементу управления до тех пор, пока не будут введены допустимые данные. Это правильное поведение диалогового окна; пользователь должен иметь возможность свободно перемещаться по элементам управления в диалоговом окне, независимо от того, правильны ли введенные данные. Однако это означает, что пользователь может ввести недопустимые данные и нажать кнопку **ОК** . По этой причине код также должен проверять все элементы управления в диалоговом окне, когда нажата кнопка **ОК** , обрабатывая событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Этот код перечисляет все объекты зависимостей в окне и, если какие-либо из них являются недопустимыми (возвращенные <xref:System.Windows.Controls.Validation.GetHasError%2A>, недопустимый элемент управления получает фокус, метод `IsValid` возвращает `false`, и окно считается недопустимым.  
  
Если диалоговое окно является допустимым, оно может быть безопасно закрыто и выполнен возврат. В рамках процесса возврата необходимо возвращать результат в вызывающую функцию.  
  
#### <a name="setting-the-modal-dialog-result"></a>Установка результата модального диалогового окна

Открытие диалогового окна с помощью <xref:System.Windows.Window.ShowDialog%2A> является фундаментальным способом, аналогичным вызову метода: код, открывший диалоговое окно с помощью <xref:System.Windows.Window.ShowDialog%2A>, ждет, пока <xref:System.Windows.Window.ShowDialog%2A> не вернет. Когда <xref:System.Windows.Window.ShowDialog%2A> возвращает, код, вызвавший его, должен решить, следует ли продолжать обработку или остановить обработку в зависимости от того, нажал ли пользователь кнопку **ОК** или кнопку **Отмена** . Чтобы упростить это решение, диалоговое окно должно вернуть выбор пользователя в виде <xref:System.Boolean> значения, возвращаемого методом <xref:System.Windows.Window.ShowDialog%2A>.  

При нажатии кнопки **ок** <xref:System.Windows.Window.ShowDialog%2A> должен возвращать `true`. Это достигается путем задания свойства <xref:System.Windows.Window.DialogResult%2A> диалогового окна при нажатии кнопки **ОК** .  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Обратите внимание, что установка свойства <xref:System.Windows.Window.DialogResult%2A> также приводит к автоматическому закрытию окна, что устраняет необходимость явно вызывать <xref:System.Windows.Window.Close%2A>.  
  
При нажатии кнопки **"Отмена"** <xref:System.Windows.Window.ShowDialog%2A> должен возвращать `false`, что также требует установки свойства <xref:System.Windows.Window.DialogResult%2A>.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Если свойство <xref:System.Windows.Controls.Button.IsCancel%2A> кнопки имеет значение `true` и пользователь нажимает кнопку « **Отмена** » или клавишу ESC, <xref:System.Windows.Window.DialogResult%2A> автоматически устанавливается в `false`. Следующая разметка действует так же, как и предыдущий код, без необходимости в обработке события <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Диалоговое окно автоматически возвращает `false`, когда пользователь нажимает кнопку **Закрыть** в строке заголовка или выбирает пункт меню **Закрыть** в **системном** меню.  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Обработка данных, возвращаемых из модального диалогового окна  

Когда <xref:System.Windows.Window.DialogResult%2A> задается в диалоговом окне, функция, которая открыла ее, может получить результат диалогового окна, проверив свойство <xref:System.Windows.Window.DialogResult%2A>, когда <xref:System.Windows.Window.ShowDialog%2A> возвращает.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Если результат диалогового окна `true`, функция использует его в качестве подсказки для получения и обработки данных, предоставленных пользователем.  
  
> [!NOTE]
> После возврата <xref:System.Windows.Window.ShowDialog%2A> диалоговое окно нельзя открыть повторно. Вместо этого придется создать новый экземпляр.

Если результат диалогового окна `false`, функция должна завершить обработку соответствующим образом.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Создание немодального настраиваемого диалогового окна

Немодальное диалоговое окно, например диалоговое окно поиска, показанное на следующем рисунке, в основном имеет такой же внешний вид, как и модальное диалоговое окно.  

![Снимок экрана, на котором отображается диалоговое окно "найти".](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Однако поведение несколько отличается, как показано в следующих разделах.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Открытие немодального диалогового окна

Немодальное диалоговое окно открывается путем вызова метода <xref:System.Windows.Window.Show%2A>.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  
 
[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

В отличие от <xref:System.Windows.Window.ShowDialog%2A><xref:System.Windows.Window.Show%2A> возвращается немедленно. Следовательно, вызывающее окно не может определить, когда немодальное диалоговое окно закрывается, и поэтому не знает, когда следует проверить результат диалогового окна или получить данные из диалогового окна для дальнейшей обработки. Поэтому диалоговому окну необходимо создать альтернативный способ возврата данных в вызывающее окно для обработки.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Обработка данных, возвращенных из немодального диалогового окна  

В этом примере `FindDialogBox` может вернуть один или несколько результатов поиска в главное окно в зависимости от искомого текста без какой бы то ни было определенной частоты. Как и в случае с модальным диалоговым окном, немодальное диалоговое окно может возвращать результаты с помощью свойств. Однако окну, которому принадлежит данное диалоговое окно, нужно знать, когда следует проверять эти свойства. Один из способов сделать это — реализовать для диалогового окна событие, которое возникает всякий раз, когда текст найден. `FindDialogBox` реализует `TextFoundEvent` для этой цели, для которой сначала требуется делегат.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

С помощью делегата `TextFoundEventHandler` `FindDialogBox` реализует `TextFoundEvent`.
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Следовательно, `Find` может вызвать событие при обнаружении результата поиска.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

Затем окну-владельцу нужно зарегистрировать и обработать это событие.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Закрытие немодального диалогового окна

Поскольку <xref:System.Windows.Window.DialogResult%2A> не нужно задавать, немодальное диалоговое окно можно закрыть с помощью механизмов, предоставляемых системой, включая следующие:  
  
- Нажатие кнопки **Закрыть** в строке заголовка.  
  
- Нажатие клавиш ALT+F4.  
  
- В меню **система** выберите пункт **Закрыть** .  
  
Кроме того, код может вызвать <xref:System.Windows.Window.Close%2A> при нажатии кнопки **Закрыть** .  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>См. также

- [Общие сведения о контекстном меню](../controls/popup-overview.md)
- [Пример диалогового окна](https://go.microsoft.com/fwlink/?LinkID=159984)
