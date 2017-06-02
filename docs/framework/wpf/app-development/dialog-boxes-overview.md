---
title: "Общие сведения о диалоговых окнах | Microsoft Docs"
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
  - "безрежимные диалоговые окна"
  - "диалоговые окна"
  - "окна сообщений"
  - "модальные диалоговые окна"
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Общие сведения о диалоговых окнах
Автономные приложения обычно имеют главного окна, что оба отображает основных данных, по которому приложение работает и предоставляет функциональные возможности для обработки данных через [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] механизмы, такие как строки меню, панелей инструментов и строки состояния. Нетривиальное приложение может также отображать дополнительные окна для следующих:  
  
-   Отображение конкретных сведений для пользователей.  
  
-   Соберите информацию от пользователей.  
  
-   И отображение и сбор сведений.  
  
 ОС Windows, известных как *диалоговые окна*, существует два типа: модальные и немодальные.  
  
 Объект *модального* диалоговое окно отображается функцией, когда она требует дополнительные данные от пользователя для продолжения. Поскольку функция зависит от модальным диалоговым окном для сбора данных, модальным диалоговым окном также не позволяет пользователю активацию других окон в приложении, пока она остается открытой. В большинстве случаев модальным диалоговым окном разрешает пользователю оповещать о завершении работы с модальным диалоговым окном, либо нажав **ОК** или **отменить** кнопки. Нажав клавишу **ОК** кнопка показывает, что пользователь ввел данные и желает, чтобы функция продолжить обработку данных. Нажав клавишу **отменить** кнопка показывает, что пользователь хочет остановить выполнение функции. Наиболее распространенными примерами модальные диалоговые окна отображаются для открытия, сохранения и печати данных.  
  
 Объект *немодальное* диалоговом с другой стороны, не запрещает пользователю активацию других окон, когда он открыт. Например если пользователь желает найти вхождения конкретного слова в документе, главное окно часто откройте диалоговое окно с запросом слова для поиска. Поскольку поиск слова не запрещает редактирование документа пользователем, тем не менее, не быть модальное диалоговое окно. Немодальное диалоговое окно содержит по крайней мере **закрыть** кнопку, чтобы закрыть диалоговое окно и может предоставлять дополнительные кнопки для выполнения отдельных функций, таких как **Найти далее** кнопку, чтобы найти следующее слово, которое соответствует критерию поиска.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]позволяет создавать несколько типов диалоговых окон, включая окна сообщений, общие диалоговые окна и пользовательские диалоговые окна. В этом разделе обсуждаются и [пример диалогового окна](http://go.microsoft.com/fwlink/?LinkID=159984) содержатся соответствующие примеры.  
  
   
  
<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Окна сообщений  
 Объект *окно сообщения* является диалоговым окном, которое можно использовать для отображения текстовых данных и разрешить пользователям принимать решения с помощью кнопок. На следующем рисунке показана окно сообщения, отображающее текстовые сведения, вопрос, который предоставляет пользователю три кнопки для ответа на вопрос.  
  
 ![Диалоговое окно «текстовый редактор»](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure1.png "DialogBoxesOverviewFigure1")  
  
 Для создания окна сообщения, используйте <xref:System.Windows.MessageBox> класса.                  <xref:System.Windows.MessageBox> позволяет настроить текст в окне сообщения, заголовок, значок и кнопки, с помощью следующего кода.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Чтобы отобразить окно сообщения, вызовите `static` <xref:System.Windows.MessageBox.Show%2A> метода, как показано в следующем коде.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Когда код, который показывает окно сообщения необходимо определить и обработать решение пользователя (какая кнопка была нажата), он может проверить результат окна сообщения, как показано в следующем коде.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Дополнительные сведения об использовании окон сообщений см. в разделе <xref:System.Windows.MessageBox>, [MessageBox образец](http://go.microsoft.com/fwlink/?LinkID=160023), и [пример диалогового окна](http://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Хотя <xref:System.Windows.MessageBox> может быть предоставлена возможность простого диалогового окна поле взаимодействие с пользователем, преимущество использования <xref:System.Windows.MessageBox> , является единственным типом окна, которое может быть отображено приложениями, выполняемыми в песочнице с частичным доверием (см. [безопасности](../../../../docs/framework/wpf/security-wpf.md)), такие как [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
 Большинство диалоговых отображения и сбора данных сложнее, чем результат окна сообщения, включая текст, выбор (флажки) взаимно исключают друг друга (переключатели) и список выбора (списки, поля со списком, раскрывающегося списка поля). Для этого [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет несколько общих диалоговых окон и позволяет создавать пользовательские диалоговые окна, хотя их использование ограничено приложениями, выполняющимися с полным доверием.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Общие диалоговые окна  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]реализует различные многократно используемые диалоговые окна, которые являются общими для всех приложений, включая диалоговые окна для открытия, сохранения файлов и печати. Поскольку эти диалоговые реализованы операционной системой, они могут совместно использоваться все приложения, работающие на операционную систему, которая помогает пользовательского интерфейса согласованности; Когда пользователи знакомы с использованием диалогового окна операционной системы в одном приложении, не нужно научиться пользоваться этим диалоговым окном в других приложениях. Поскольку эти диалоговые доступны для всех приложений и обеспечивают пользователю согласованный интерфейс, они называются *общие диалоговые окна*.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]Инкапсулирует открыть файл, сохраните файл и печати общие диалоговые окна и представляет их как управляемые классы для использования в самостоятельных приложениях. Этот раздел содержит краткий обзор каждого.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Диалоговое окно открытия файлов  
 Диалоговое окно открытия, показано на следующем рисунке, используется функциональными возможностями открытия файла для извлечения имени файла, чтобы открыть.  
  
 ![Откройте диалоговое окно](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure2.png "DialogBoxesOverviewFigure2")  
  
 Стандартным диалоговым окном открытия реализуется как <xref:Microsoft.Win32.OpenFileDialog> класса и находится в <xref:Microsoft.Win32> пространства имен. В следующем коде показано, как создавать, настраивать и показывать один и способы обработки результата.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Дополнительные сведения о диалоговом окне Открытие файла в разделе <xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName>.  
  
> [!NOTE]
>  <xref:Microsoft.Win32.OpenFileDialog> может использоваться для безопасного извлечения имен файлов приложениями, выполняемыми в режиме частичного доверия (см. [безопасности](../../../../docs/framework/wpf/security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>Сохранение файла-диалоговое окно  
 Сохранить диалоговое окно файла, показано на следующем рисунке, используется функциональными возможностями сохранения файла необходимо получить имя файла для сохранения.  
  
 ![Диалоговое окно «Сохранить как»](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure3.png "DialogBoxesOverviewFigure3")  
  
 Общий файл диалоговое окно сохранения реализуется как <xref:Microsoft.Win32.SaveFileDialog> класса и находится в <xref:Microsoft.Win32> пространства имен. В следующем коде показано, как создавать, настраивать и показывать один и способы обработки результата.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Дополнительные сведения о сохранении диалоговое окно файла см. в разделе <xref:Microsoft.Win32.SaveFileDialog?displayProperty=fullName>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Диалоговое окно Печать  
 Диалоговом окне печати, показано на следующем рисунке, используется функциональными возможностями печати для выбора и настройки принтера для печати данных для которых пользователь.  
  
 ![Диалоговое окно печати](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure4.png "DialogBoxesOverviewFigure4")  
  
 Общее диалоговое окно печати реализуется как <xref:System.Windows.Controls.PrintDialog> класса и находится в <xref:System.Windows.Controls> пространства имен. Ниже показано, как создавать, настраивать и показывать один.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Дополнительные сведения о диалоговом окне печати см. в разделе <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName>. Подробное описание печати в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], в разделе [Обзор печати](../../../../docs/framework/wpf/advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Пользовательские диалоговые окна  
 Хотя общие диалоговые окна полезны и должен использоваться, когда это возможно, они не поддерживают требования диалоговых окон отдельного домена. В этих случаях необходимо создать собственные диалоговые окна. Как мы увидим, диалоговое окно является окном с отдельными поведениями.                  <xref:System.Windows.Window> это поведение реализуется и, следовательно, используют <xref:System.Windows.Window> для создания пользовательских модальных и немодальных диалоговых окон.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Создание модального настраиваемого диалогового окна  
 В этом разделе показано, как использовать <xref:System.Windows.Window> для создания реализации типичного модального диалогового окна с помощью `Margins` диалоговое окно в качестве примера (см. [пример диалогового окна](http://go.microsoft.com/fwlink/?LinkID=159984)). `Margins` Диалоговое окно показано на следующем рисунке.  
  
 ![Диалоговое окно «поля»](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure5.png "DialogBoxesOverviewFigure5")  
  
#### <a name="configuring-a-modal-dialog-box"></a>Настройка модального диалогового окна  
 Пользовательский интерфейс для диалогового окна обычно включает следующее:  
  
-   Различные элементы управления, которые необходимы для сбора нужных данных.  
  
-   Отображение **ОК** кнопки, что пользователи щелкните, чтобы закрыть диалоговое окно, вернуться к функции и продолжить обработку.  
  
-   Отображение **отменить** кнопки, пользователь нажимает, чтобы закрыть диалоговое окно и остановить дальнейшую обработку функции.  
  
-   Отображение **закрыть** кнопки в заголовке окна.  
  
-   Отображение значка.  
  
-   Showing                                          **Minimize**,                                          **Maximize**, and                                          **Restore** buttons.  
  
-   Отображение **системы** меню, чтобы свести к минимуму, развернуть, восстановление и закрыть диалоговое окно.  
  
-   Открытие выше и в центре окна, которое открывается диалоговое окно.  
  
-   Диалоговые окна регулируемого размера, где это возможно, поэтому для предотвращения окно слишком мал и предоставить пользователю размер полезные значения по умолчанию, необходимо установить по умолчанию и не менее измерения следует соответственно.  
  
-   Нажатие клавиши ESC следует настроить как сочетание клавиш, которое вызывает **отменить** нажатие кнопки. Это достигается путем установки <xref:System.Windows.Controls.Button.IsCancel%2A> свойство **отменить** кнопки `true`.  
  
-   Нажав клавишу ВВОД (или возврата) настраивается, как сочетание клавиш, которое вызывает **ОК** нажатие кнопки. Это достигается путем установки <xref:System.Windows.Controls.Button.IsDefault%2A> свойство **ОК** кнопку `true`.  
  
 Следующий код демонстрирует эту конфигурацию.  
  
 [!code-xml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup1)]  
[!code-xml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup2)]  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind2)]  
  
 В строке меню окна, которое открывает диалоговое окно также расширяет интерфейс пользователя для диалогового окна. Когда элемент меню выполняет функцию, которая требует взаимодействия пользователя с диалоговым окном перед продолжением функции, элемент меню для функции будет иметь многоточие в заголовке, как показано ниже.  
  
 [!code-xml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup1)]  
[!code-xml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup2)]  
  
 Когда элемент меню выполняет функцию, которая отображает диалоговое окно, которое не требует вмешательства пользователя, такие как диалоговое окно "о программе", многоточие не требуется.  
  
#### <a name="opening-a-modal-dialog-box"></a>Открытие модального диалогового окна  
 Диалоговое окно обычно отображается в результате выбора пользователем элемента меню для выполнения функции конкретного домена, например Установка полей документа в текстовом процессоре. Показывать как диалоговое окно похоже на отображение обычного окна, хотя она требует дополнительных диалогового окна Настройка. Весь процесс создания, настройки и открытие диалогового окна отображается в следующем коде.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind4)]  
  
 Здесь код передает сведения по умолчанию (о текущих полях) в диалоговое окно. Он также задает <xref:System.Windows.Window.Owner%2A?displayProperty=fullName> свойство со ссылкой на окно, которое отображает диалоговое окно. Как правило, следует всегда устанавливать владельца диалоговое окно, чтобы задать поведения, связанные с состоянием окна, общие для всех диалоговых окнах (см. [Обзор Windows WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md) Дополнительные сведения).  
  
> [!NOTE]
>  Необходимо задать владельца для поддержки [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] автоматизации для диалоговых окон (см. [обзор автоматизации пользовательского интерфейса](../../../../docs/framework/ui-automation/ui-automation-overview.md)).  
  
 После настройки диалогового она отображается как модальная путем вызова <xref:System.Windows.Window.ShowDialog%2A> метод.  
  
#### <a name="validating-user-provided-data"></a>Проверка пользовательских данных  
 Если открывается диалоговое окно и пользователь предоставляет требуемые данные, диалоговое окно отвечает за обеспечение допустимость предоставленного данных по следующим причинам:  
  
-   С точки зрения безопасности следует проверять все входные данные.  
  
-   С точки зрения конкретного домена проверка данных запрещает обрабатывается в коде, который потенциально может выдавать исключения ошибочные данные.  
  
-   С точки зрения взаимодействия с пользователем диалоговое окно может помочь пользователям, показывающая, какие данные будут введены недопустимые.  
  
-   С точки зрения производительности проверка данных в многоуровневое приложение можно уменьшить количество циклов обработки между клиентом и уровнями приложения, особенно в том случае, если приложение состоит из веб-служб и серверных баз данных.  
  
 Чтобы проверить связанный элемент управления в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], необходимо определить правило проверки и связать его с привязкой. Правило проверки — пользовательский класс, производный от <xref:System.Windows.Controls.ValidationRule>. В следующем примере показано правило проверки, `MarginValidationRule`, которое проверяет, что связанным значением является <xref:System.Double> и находится в пределах указанного диапазона.  
  
 [!code-csharp[DialogBoxSample#MarginValidationRuleCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs#marginvalidationrulecode)]
 [!code-vb[DialogBoxSample#MarginValidationRuleCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb#marginvalidationrulecode)]  
  
 В этом коде логика правила проверки реализована путем переопределения <xref:System.Windows.Controls.ValidationRule.Validate%2A> метода, который проверяет данные и возвращает соответствующий <xref:System.Windows.Controls.ValidationResult>.  
  
 Чтобы связать правило проверки со связанным элементом управления, используйте следующую разметку.  
  
 [!code-xml[DialogBoxSample#MarginsValidationMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup1)]  
[!code-xml[DialogBoxSample#MarginsValidationMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup2)]  
[!code-xml[DialogBoxSample#MarginsValidationMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup3)]  
  
 После установления связи правила проверки, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] автоматически применяет его при вводе данных в связанный элемент управления. Если элемент управления содержит недопустимые данные [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] отображает красные границы вокруг недопустимого элемента, как показано на следующем рисунке.  
  
 ![Недопустимая левая граница](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure7.png "DialogBoxesOverviewFigure7")  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]не ограничивает пользователя недопустимым элементом управления, пока не будут введены допустимые данные. Это нормальное поведение диалогового окна; пользователь должен иметь возможность свободно перемещаться между элементами управления в диалоговом окне ли данные недопустимы. Тем не менее, это означает, пользователь может ввести недопустимые данные и нажмите клавишу **ОК** кнопки. По этой причине код также должен проверить все элементы управления в диалоговом окне когда **ОК** путем обработки нажата кнопка <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind3)]  
  
 Этот код перечисляет все зависимые объекты в окне и, если какой-либо недопустимые (возвращаемый <xref:System.Windows.Controls.Validation.GetHasError%2A>, недопустимый элемент управления получает фокус, `IsValid` возвращает метод `false`, и окно считается недопустимым.  
  
 Когда диалоговое окно является допустимым, может безопасно закрыть и вернуть. В рамках процесса возврата он должен возвращать результат вызывающей функции.  
  
#### <a name="setting-the-modal-dialog-result"></a>Задание результата модального диалогового окна  
 Открытие диалогового окна при помощи <xref:System.Windows.Window.ShowDialog%2A> существенно аналогичен вызову метода: код, открывается диалоговое окно с помощью <xref:System.Windows.Window.ShowDialog%2A> ожидает <xref:System.Windows.Window.ShowDialog%2A> возвращает. При <xref:System.Windows.Window.ShowDialog%2A> возвращает, код, который вызвал его должна решить, следует ли продолжить или прекратить обработку, на основе ли пользователь нажал **ОК** кнопку или **отменить** кнопки. Для облегчения принятия этого решения, диалоговое окно должно возвращать выбора пользователя как <xref:System.Boolean> значение, возвращенное из <xref:System.Windows.Window.ShowDialog%2A> метод.  
  
 Когда **ОК** нажатии кнопки <xref:System.Windows.Window.ShowDialog%2A> должен вернуть `true`. Это достигается путем установки <xref:System.Windows.Window.DialogResult%2A> поле свойства в диалоговом окне, когда **ОК** кнопки.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind3)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind4)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind4)]  
  
 Обратите внимание, что <xref:System.Windows.Window.DialogResult%2A> свойство также вызывает автоматическое закрытие окна, что устраняет необходимость явно вызывать <xref:System.Windows.Window.Close%2A>.  
  
 При **отменить** нажатии кнопки <xref:System.Windows.Window.ShowDialog%2A> должен вернуть `false`, что также требует настройки <xref:System.Windows.Window.DialogResult%2A> свойство.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind3)]  
  
 Когда кнопка <xref:System.Windows.Controls.Button.IsCancel%2A> свойству `true` и пользователь нажимает клавишу **отменить** кнопки или клавиши ESC <xref:System.Windows.Window.DialogResult%2A> автоматически устанавливается значение `false`. Следующая разметка действует так же, как предыдущий код, без необходимости обрабатывать <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события.  
  
 [!code-xml[DialogBoxSample#MarginsDialogDefaultCancelMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogdefaultcancelmarkup)]  
  
 Диалоговое окно автоматически возвращает `false` при нажатии клавиши **закрыть** кнопки в строке заголовка или выбирает **закрыть** элемент меню из **системы** меню.  
  
#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Обработка данных, возвращенных из модального диалогового окна  
 Когда <xref:System.Windows.Window.DialogResult%2A> установлено диалоговым окном, функция, которая открыла его можно получить результат диалогового окна путем проверки <xref:System.Windows.Window.DialogResult%2A> свойства при <xref:System.Windows.Window.ShowDialog%2A> возвращает.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind4)]  
  
 Если результатом диалогового окна является `true`, функция использует его в качестве подсказки для получения и обработки данных, предоставленных пользователем.  
  
> [!NOTE]
>  После <xref:System.Windows.Window.ShowDialog%2A> вернула, нельзя снова открыть диалоговое окно. Вместо этого необходимо создать новый экземпляр.  
  
 Если результатом диалогового окна является `false`, функция должна соответствующим образом закончить обработку.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Создание немодального настраиваемого диалогового окна  
 Немодальное диалоговое такие как найти диалоговое окно показано на следующем рисунке, имеет такой же внешний вид как модальное диалоговое окно.  
  
 ![Диалоговое окно '' Поиск](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure6.PNG "DialogBoxesOverviewFigure6")  
  
 Однако поведение несколько отличается, как описано в следующих разделах.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Открытие немодального диалогового окна  
 Немодальное диалоговое окно открывается вызовом <xref:System.Windows.Window.Show%2A> метод.  
  
 [!code-xml[DialogBoxSample#OpenFindDialogMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#openfinddialogmarkup1)]  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind3)]  
  
 В отличие от <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> возвращается немедленно. Следовательно вызывающее окно не может определить, когда безрежимное диалоговое окно закрывается и, следовательно, не знает, когда поиск результат диалогового окна или получить данные из диалогового окна для дальнейшей обработки. Вместо этого окно требуется создать альтернативный способ возвращения данных в вызывающее окно для обработки.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Обработка данных, возвращаемых из немодального диалогового окна  
 В этом примере `FindDialogBox` может возвращать один или несколько найти результаты в главное окно, в зависимости от текста, поиск которого выполняется без определенного интервала времени. Как и в случае с модальным диалоговым окном, немодального диалогового окна может возвращать результаты с помощью свойств. Однако, которому принадлежит данное диалоговое окно необходимо знать, когда следует проверять эти свойства. Один из способов — для диалогового окна реализовать событие, которое возникает, когда текст найден.                                  `FindDialogBox`реализует `TextFoundEvent` для этой цели, которое вначале требует делегата.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventHandlerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs#textfoundeventhandlercode)]
 [!code-vb[DialogBoxSample#TextFoundEventHandlerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb#textfoundeventhandlercode)]  
  
 Using the                                  `TextFoundEventHandler` delegate,                                  `FindDialogBox` implements the                                  `TextFoundEvent`.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind2)]  
  
 Следовательно `Find` может вызывать событие, когда найден результат поиска.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind2)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind3)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind3)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind4)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind4)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind5)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind5)]  
  
 Окно владельца затем необходимо зарегистрировать и обработать это событие.  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind2)]  
  
#### <a name="closing-a-modeless-dialog-box"></a>Закрытие немодального диалогового окна  
 Поскольку <xref:System.Windows.Window.DialogResult%2A> не требуется устанавливать, немодальное диалоговое окно можно закрыть с помощью системы предоставляют механизмы, включая следующие:  
  
-   Щелкнув **закрыть** кнопки в заголовке окна.  
  
-   Клавиши ALT + F4.  
  
-   Choosing                                          **Close** from the                                          **System** menu.  
  
 Кроме того, код может вызвать <xref:System.Windows.Window.Close%2A> при **закрыть** кнопки.  
  
 [!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind1)]
 [!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind1)]  
[!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind2)]
[!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind2)]  
  
## <a name="see-also"></a>См. также  
 [Обзор всплывающего окна](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [Пример диалогового окна](http://go.microsoft.com/fwlink/?LinkID=159984)   
 [Пример ColorPicker пользовательского элемента управления](http://go.microsoft.com/fwlink/?LinkID=159977)