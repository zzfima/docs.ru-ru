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
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187457"
---
# <a name="dialog-boxes-overview"></a>Обзор диалоговые коробки
Автономные приложения обычно имеют основное окно, которое отображает основные данные, над которыми [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] работает приложение, и предоставляет функциональность для обработки этих данных через такие механизмы, как бары меню, бары инструментов и полосы состояния. Нетривиальное приложение может также отображать дополнительные окна для следующих целей:  
  
- отображения определенных сведений для пользователей;  
  
- сбора сведений от пользователей;  
  
- сбора и отображения сведений.  
  
 Эти типы окон известны как *диалоговые окна,* и есть два типа: модальный и безрежимный.  
  
 *Модальный* диалоговый ящик отображается функцией, когда функция нуждается в дополнительных данных от пользователя для продолжения. Поскольку функция зависит от модального диалогового окна для сбора данных, это окно также не разрешает пользователю активизировать другие окна в приложении, пока остается открытым. В большинстве случаев модальный диалоговый ящик позволяет пользователю сигнализировать, когда он закончит с модальным диалоговым окном, нажав кнопку **OK** или **Cancel.** Нажатие кнопки **OK** указывает на то, что пользователь ввел данные и хочет, чтобы функция продолжала обрабатывать эти данные. Нажатие кнопки **«Отмена»** указывает на то, что пользователь хочет полностью остановить выполнение функции. Наиболее распространенными примерами модальных диалоговых окон являются окна, которые отображаются для открытия, сохранения и печати данных.  
  
 С другой стороны, *безрежимная* диалоговая коробка не мешает пользователю активировать другие окна во время его работы. Например, если пользователь хочет найти вхождения конкретного слова в документе, главное окно часто открывает диалоговое окно с запросом слова для поиска. Так как поиск слова не мешает пользователю редактировать документ, диалоговое окно не обязательно должно быть модальным. Безрежимный диалоговый ящик, по крайней мере, предоставляет кнопку **«Закрыть»** для закрытия диалогового окна и может предоставить дополнительные кнопки для выполнения определенных функций, таких как кнопка **«Найти следующую»,** чтобы найти следующее слово, которое соответствует критериям поиска слов.  
  
 Windows Presentation Foundation (WPF) позволяет создавать несколько типов диалоговых коробок, включая ящики с сообщениями, общие диалоговые ящики и пользовательские диалоговые коробки. Эта тема обсуждает каждый из них, и [образец Dialog Box](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) приводит соответствующие примеры.  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>Коробки сообщений  
 *Коробка сообщений* — это диалоговое окно, которое может использоваться для отображения текстовой информации и для того, чтобы пользователи могли принимать решения с помощью кнопок. На следующем рисунке показано окно сообщения, в котором отображается текстовая информация, задается вопрос и предоставляются три кнопки для ответа на этот вопрос.  
  
 ![Диалог-поле Word Processor с вопросом, хотите ли вы сохранить изменения в документе до закрытия приложения.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Для создания окна сообщений <xref:System.Windows.MessageBox> используется класс. <xref:System.Windows.MessageBox>позволяет настроить текст коробки сообщений, название, значок и кнопки, используя код, как следующее.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Чтобы показать окно сообщений, `static` <xref:System.Windows.MessageBox.Show%2A> вы называете метод, как показано в следующем коде.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Когда коду, который показывает окно сообщения, нужно определить и обработать решение пользователя (какая кнопка была нажата), он может проверить результат окна сообщения, как показано в следующем коде.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Для получения дополнительной информации <xref:System.Windows.MessageBox>об использовании ящиков сообщений см., [Образец MessageBox](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)и [образец Dialog Box](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).  
  
 Хотя <xref:System.Windows.MessageBox> может предложить простой диалоговый ящик <xref:System.Windows.MessageBox> с пользователем, преимущество использования заключается в том, что это единственный тип окна, который может быть показан приложениями, которые работают в пределах частичной песочницы безопасности доверия (см. [Безопасность),](../security-wpf.md)таких как приложения для браузеров XAML (XBAPs).  
  
 Большинство диалоговых окон отображают и собирают более сложные данные, чем результат окна сообщения, в том числе текст, выбранные варианты (флажки), взаимоисключающий выбор (переключатели) и списки выбора (списки, поля со списком, поля с раскрывающимся списком). Для них Windows Presentation Foundation (WPF) предоставляет несколько общих диалоговых коробок и позволяет создавать собственные диалоговые коробки, хотя использование любого из них ограничено приложениями, работающими с полным доверием.  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>Общие диалоговые ящики  
 Windows реализует различные многоразовые диалоговые файлы, которые являются общими для всех приложений, включая диалоговые окна для открытия файлов, сохранения файлов и печати. Поскольку эти диалоговые окна реализованы операционной системой, они могут совместно использоваться всеми приложениями, работающими в операционной системе, что помогает поддерживать единообразие пользовательского интерфейса; если пользователи знакомы с диалоговым окном, предоставляемым операционной системой в одном приложении, им не нужно учиться пользоваться этим диалоговым окном в других приложениях. Поскольку эти диалоговые коробки доступны для всех приложений и поскольку они помогают обеспечить согласованный пользовательский опыт, они известны как *общие диалоговые коробки.*  
  
 Фонд презентаций Windows (WPF) инкапсулирует открытый файл, сохраняет файл и печатает общие диалоговые файлы и предоставляет их в качестве управляемых классов для использования в автономных приложениях. В этом разделе приводится краткий обзор каждого типа диалоговых окон.  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>Диалог открытого файла  
 Диалоговое окно открытия файлов, показанное на следующем рисунке, используется функциональностью открытия файла для получения имени открываемого файла.  
  
 ![Открытое поле диалога, показывающее местоположение для извлечения файла.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 Общий открытый файл диалогового <xref:Microsoft.Win32.OpenFileDialog> окна реализован как <xref:Microsoft.Win32> класс и находится в пространстве имен. Следующий код показывает, как создавать, настраивать и отображать такое окно, а также как обрабатывать результат.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Для получения дополнительной информации об открытом <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>файле диалогового окна см.  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>могут быть использованы для безопасного получения имен файлов приложениями, работающими с частичным доверием (см. [Безопасность).](../security-wpf.md)  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>диалоговое окно сохранения файлов  
 Диалоговое окно сохранения файлов, показанное на следующем рисунке, используется функциональностью сохранения файла для получения имени сохраняемого файла.  
  
 ![Файл диалога «Сохранить как диалог», показывающий местоположение для сохранения файла.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Общий файл диалогового файла <xref:Microsoft.Win32.SaveFileDialog> сохраняется как класс <xref:Microsoft.Win32> и находится в пространстве имен. Следующий код показывает, как создавать, настраивать и отображать такое окно, а также как обрабатывать результат.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Для получения дополнительной информации о файле диалогового окна сохранить см. <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>Печать - диалоговое окно

Диалоговое окно печати, показанное на следующем рисунке, используется функциональными возможностями печати для выбора и настройки принтера, на котором пользователь хочет печатать данные.  
  
![Скриншот, на который изображен диалоговый ящик print.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
Общий диалоговый ящик печати <xref:System.Windows.Controls.PrintDialog> реализован как класс и <xref:System.Windows.Controls> находится в пространстве имен. Следующий код показывает, как создавать, настраивать и отображать такое окно.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Для получения дополнительной информации о <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>печати диалоговые окна, см. Для детального обсуждения печати в WPF [см.](../advanced/printing-overview.md)  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>Пользовательские диалоговые коробки

Хотя общие диалоговые окна полезны и должны использоваться, когда это возможно, они не поддерживают требований диалоговых окон отдельного домена. В этих случаях необходимо создавать собственные диалоговые окна. Как мы увидим, диалоговое окно является окном со специальным поведением. <xref:System.Windows.Window>реализует эти поведения и, следовательно, <xref:System.Windows.Window> вы используете для создания пользовательских модальных и бесрежимных диалоговых коробок.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>Создание модального пользовательского диалогового окна

В этой теме <xref:System.Windows.Window> показано, как использовать для создания типичной реализации модального диалогового окна, используя `Margins` в качестве примера диалоговую коробку (см. [образец Dialog Box).](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) Диалоговая `Margins` коробка отображается на следующей рисунке.  
  
 ![Диалог margins с полями для определения левой маржи, верхней маржи, правой маржи и нижней.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Настройка модального диалогового окна

Пользовательский интерфейс для типичного диалогового окна включает следующее.  
  
- Различные элементы управления, которые необходимы для сбора нужных данных.  
  
- **Кнопка OK,** на которую нажимают пользователи, чтобы закрыть диалоговую будку, вернуться к функции и продолжить обработку.  
  
- **Кнопка «Отмена»,** на которую нажимают пользователи, чтобы закрыть диалоговую будку и остановить дальнейшую обработку функции.  
  
- **Кнопка "Закрыть"** в заглавной панели.  
  
- Значок.  
  
- **Минимизировать,** **максимизировать**и **восстановить** кнопки.  
  
- **Меню системы** для минимизации, максимизации, восстановления и закрытия диалогового окна.  
  
- Положение выше и в центре окна, открыващее диалоговую будку.  
  
- Возможность переразмерировать, где это возможно, чтобы предотвратить слишком малую диалоговую коробку и предоставить пользователю полезный размер по умолчанию. Для этого необходимо установить как значение по умолчанию, так и минимальные размеры.  
  
- Ключ ESC как ярлык клавиатуры, который вызывает нажатие кнопки **Отмена.** Вы делаете это, <xref:System.Windows.Controls.Button.IsCancel%2A> установив свойство `true`кнопки **Отмена** .  
  
- Ключ ENTER (или RETURN) в качестве ярлыка клавиатуры, который вызывает нажатие кнопки **OK.** Вы делаете это, <xref:System.Windows.Controls.Button.IsDefault%2A> устанавливая свойство кнопки `true` **OK.**  
  
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

В данном случае код передает информацию по умолчанию (текущая поля) в поле диалога. Он также <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> устанавливает свойство со ссылкой на окно, которое показывает диалоговую коробку. В общем, необходимо всегда устанавливать владельца для диалогового окна, чтобы обеспечить поведение, связанное с состоянием окон, которые являются общими для всех диалоговых коробок (подробнее [см. обзор WPF Windows).](wpf-windows-overview.md)

> [!NOTE]
> Необходимо предоставить владельцу систему поддержки автоматизации пользовательского интерфейса (Пользовательского интерфейса) для диалоговые поля [(см. Обзор автоматизации пользовательского интерфейса).](../../ui-automation/ui-automation-overview.md)

После настройки диалогового окна он отображается модально, вызывая <xref:System.Windows.Window.ShowDialog%2A> метод.  
  
#### <a name="validating-user-provided-data"></a>Проверка данных, предоставленных пользователями

Если открывается диалоговое окно и пользователь предоставляет требуемые данные, диалоговое окно отвечает за проверку допустимости предоставленных данных по следующим причинам.  
  
- С точки зрения безопасности следует проверять все входные данные.  
  
- С точки зрения конкретного домена проверка данных предотвращает обработку в коде ошибочных данных, которые могут вызывать исключения.  
  
- С точки зрения взаимодействия с пользователем диалоговое окно может помочь пользователям, показывая, какие введенные ими данные являются недопустимыми.  
  
- С точки зрения производительности проверка данных в многоуровневом приложении может уменьшить количество циклов обработки между уровнями клиента и приложения, особенно в том случае, если в приложение входят веб-службы или серверные базы данных.  

Чтобы проверить связанный элемент управления в WPF, необходимо определить правило проверки и связать его с привязкой. Правило проверки — это пользовательский <xref:System.Windows.Controls.ValidationRule>класс, который происходит от . В следующем примере показано `MarginValidationRule`правило проверки, которое <xref:System.Double> проверяет, что связанное значение является и находится в пределах заданного диапазона.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

В этом коде логика проверки правила проверки реализуется путем переопределения <xref:System.Windows.Controls.ValidationRule.Validate%2A> метода, <xref:System.Windows.Controls.ValidationResult>который проверяет данные и возвращает соответствующий.  

Чтобы сопоставить это правило проверки со связанным элементом управления, используется следующая разметка.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

После того, как правило проверки связано, WPF автоматически применяет его при входе данных в связанный контроль. Когда элемент управления содержит недействительные данные, WPF будет отображать красную границу вокруг недействительного элемента управления, как показано на следующем рисунке.  
  
![Диалогполе margins с красной границей вокруг недействительного значения левой маржи.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPF не ограничивает пользователя недействительным элементом управления до тех пор, пока он не введет действительные данные. Это правильное поведение диалогового окна; пользователь должен иметь возможность свободно перемещаться по элементам управления в диалоговом окне, независимо от того, правильны ли введенные данные. Однако это означает, что пользователь может вводить недействительные данные и нажимать кнопку **OK.** По этой причине код также должен проверять все элементы **OK** управления в диалоговом <xref:System.Windows.Controls.Primitives.ButtonBase.Click> поле при нажатии кнопки OK при обработке события.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Этот код перечисляет все объекты зависимости на окне и, если <xref:System.Windows.Controls.Validation.GetHasError%2A>они являются недействительными (как `IsValid` возвращается, недействительный элемент управления получает фокус, метод возвращается, `false`и окно считается недействительным.  
  
Если диалоговое окно является допустимым, оно может быть безопасно закрыто и выполнен возврат. В рамках процесса возврата необходимо возвращать результат в вызывающую функцию.  
  
#### <a name="setting-the-modal-dialog-result"></a>Настройка результата модального диалога

Открытие диалогового <xref:System.Windows.Window.ShowDialog%2A> окна с помощью в основном подобно вызову метода: код, открывший диалоговое окно, с помощью <xref:System.Windows.Window.ShowDialog%2A> ожидания до <xref:System.Windows.Window.ShowDialog%2A> возвращения. При <xref:System.Windows.Window.ShowDialog%2A> возврате код, который вызвал его, должен решить, продолжать ли обработку или прекратить обработку, в зависимости от того, нажал ли пользователь кнопку **OK** или **кнопку «Отмена».** Чтобы облегчить это решение, диалоговая коробка должна вернуть <xref:System.Boolean> выбор пользователя в <xref:System.Windows.Window.ShowDialog%2A> качестве значения, которое возвращается из метода.  

При **OK** нажатии кнопки <xref:System.Windows.Window.ShowDialog%2A> ОК `true`следует вернуться. Это достигается путем установки <xref:System.Windows.Window.DialogResult%2A> свойства окна диалога при нажатии кнопки **OK.**  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Обратите внимание, <xref:System.Windows.Window.DialogResult%2A> что установка свойства также приводит к автоматическому закрытию <xref:System.Windows.Window.Close%2A>окна, что облегчает необходимость явного вызова.  
  
При нажатии кнопки **Отмена,** <xref:System.Windows.Window.ShowDialog%2A> должны вернуться, `false`что также требует установки <xref:System.Windows.Window.DialogResult%2A> свойства.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

При установке <xref:System.Windows.Controls.Button.IsCancel%2A> свойства кнопки `true` и нажатия пользователем кнопки **«Отмена»** или ключа ESC <xref:System.Windows.Window.DialogResult%2A> автоматически устанавливается `false`значение. Следующая разметка имеет тот же эффект, что и <xref:System.Windows.Controls.Primitives.ButtonBase.Click> предыдущий код, без необходимости обработки события.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Диалоговая коробка `false` автоматически возвращается, когда пользователь нажимает кнопку **«Закрыть»** в заголовке или выбирает пункт меню **Close** из меню **System.**  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Обработка данных, возвращенных из модального диалогового окна  

Когда <xref:System.Windows.Window.DialogResult%2A> устанавливается диалоговая коробка, функция, которая открылась, может получить <xref:System.Windows.Window.DialogResult%2A> результат <xref:System.Windows.Window.ShowDialog%2A> диалогового окна, проинспектируя свойство при возврате.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Если результат диалога, `true`функция использует это как сигнал для извлечения и обработки данных, предоставленных пользователем.  
  
> [!NOTE]
> После <xref:System.Windows.Window.ShowDialog%2A> возвращения диалоговая будка не может быть вновь открыта. Вместо этого придется создать новый экземпляр.

Если результат диалога, `false`функция должна закончить обработку надлежащим образом.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>Создание безспособного пользовательского диалогового окна

Немодальное диалоговое окно, например диалоговое окно поиска, показанное на следующем рисунке, в основном имеет такой же внешний вид, как и модальное диалоговое окно.  

![Скриншот, на который изображена поле поиска диалога.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Однако поведение несколько отличается, как показано в следующих разделах.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Открытие безспособного диалогового окна

Безрежимная диалоговая коробка открывается путем вызова метода. <xref:System.Windows.Window.Show%2A>  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

В <xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> отличие от , возвращается немедленно. Следовательно, вызывающее окно не может определить, когда немодальное диалоговое окно закрывается, и поэтому не знает, когда следует проверить результат диалогового окна или получить данные из диалогового окна для дальнейшей обработки. Поэтому диалоговому окну необходимо создать альтернативный способ возврата данных в вызывающее окно для обработки.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Обработка данных, возвращенных из безспособного диалогового окна  

В этом примере `FindDialogBox` может вернуть один или несколько результатов поиска в основное окно, в зависимости от текста, который ищется без какой-либо конкретной частоты. Как и в случае с модальным диалоговым окном, немодальное диалоговое окно может возвращать результаты с помощью свойств. Однако окну, которому принадлежит данное диалоговое окно, нужно знать, когда следует проверять эти свойства. Один из способов сделать это — реализовать для диалогового окна событие, которое возникает всякий раз, когда текст найден. `FindDialogBox`реализует `TextFoundEvent` для этой цели, которая сначала требует делегата.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Используя `TextFoundEventHandler` делегата, `FindDialogBox` `TextFoundEvent`реализуется .
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Следовательно, `Find` может привести к возникновению события при обнаружении результата поиска.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

Затем окну-владельцу нужно зарегистрировать и обработать это событие.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Закрытие безспособного диалогового окна

Поскольку <xref:System.Windows.Window.DialogResult%2A> не нужно устанавливать, безрежимный диалог может быть закрыт с помощью системных механизмов, в том числе следующих:  
  
- Нажав кнопку **"Закрыть"** в заголовке бара.  
  
- Нажатие клавиш ALT+F4.  
  
- Выбор **Закрытия** из меню **системы.**  
  
Кроме того, код <xref:System.Windows.Window.Close%2A> может звонить при нажатии кнопки **«Закрыть».**  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>См. также раздел

- [Общие сведения о контекстном меню](../controls/popup-overview.md)
- [Пример диалогового окна](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
