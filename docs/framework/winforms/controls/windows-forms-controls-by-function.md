---
title: "Функциональная классификация элементов управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], по функциям"
  - "элементы управления Windows Forms, список"
  - "Windows Forms, элементы управления по функциям"
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Функциональная классификация элементов управления Windows Forms
В Windows Forms существуют элементы управления и компоненты, выполняющие ряд функций.  В следующей таблице представлен список компонентов и элементов управления Windows Forms в соответствии с основной функцией.  Кроме того, если для выполнения одной и той же функции служат несколько элементов управления, то рекомендуемые элементы управления перечислены с указанием использовавшихся ранее устаревших элементов управления.  Устаревшие элементы управления также перечислены в отдельной таблице; рядом с каждым таим элементом управления указан новый элемент, пришедший на смену устаревшему.  
  
> [!NOTE]
>  Следующие таблицы не являются исчерпывающим перечнем всех элементов управления и компонентов Windows Forms. Подробный перечень см. в разделе [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
## Рекомендуемые элементы управления и компоненты по функциям  
  
|Функция|Элемент управления|Описание|  
|-------------|------------------------|--------------|  
|Отображение данных|Элемент управления <xref:System.Windows.Forms.DataGridView>|Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет настраиваемую таблицу для отображения данных.  Класс <xref:System.Windows.Forms.DataGridView> обеспечивает настройку ячеек, строк, столбцов и границ таблицы. **Note:**  Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает ряд простых и сложных функций, отсутствующих в элементе управления <xref:System.Windows.Forms.DataGrid>.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).|  
|Привязка данных и перемещение|Компонент <xref:System.Windows.Forms.BindingSource>|Упрощает привязку элементов управления в форме к данным благодаря средствам управления денежными единицами, уведомлениям об изменениях и т.д.|  
||Элемент управления <xref:System.Windows.Forms.BindingNavigator>|Предоставляет интерфейс, подобный панели инструментов, для переходов по форме и управлению данными.|  
|Редактирование текста|Элемент управления <xref:System.Windows.Forms.TextBox>|Отображает текст, введенный в режиме разработки, который пользователи могут изменять во время выполнения или с помощью программных средств.|  
||Элемент управления <xref:System.Windows.Forms.RichTextBox>|Позволяет представлять текст в простом текстовом формате или в формате RTF.|  
||Элемент управления <xref:System.Windows.Forms.MaskedTextBox>|Ограничивает формат данных, вводимых пользователем.|  
|Отображение информации \(только для чтения\)|Элемент управления <xref:System.Windows.Forms.Label>|Отображает текст, недоступный для непосредственного редактирования пользователем.|  
||Элемент управления <xref:System.Windows.Forms.LinkLabel>|Отображает текст в виде веб\-ссылки и создает событие при щелчке текста.  Как правило, текст является ссылкой на другое окно или на веб\-узел.|  
||Элемент управления <xref:System.Windows.Forms.StatusStrip>|Отображает сведения о текущем состоянии приложения в окне, заключенном в рамку, обычно в нижней части родительской формы.|  
||Элемент управления <xref:System.Windows.Forms.ProgressBar>|Отображает ход выполнения текущей операции.|  
|Отображение веб\-страниц|Элемент управления <xref:System.Windows.Forms.WebBrowser>|Позволяет пользователям перемещаться по веб\-страницам внутри формы.|  
|Выбор из списка|Элемент управления <xref:System.Windows.Forms.CheckedListBox>|Отображает список с полосой прокрутки, состоящий из элементов с флажками.|  
||Элемент управления <xref:System.Windows.Forms.ComboBox>|Отображает раскрывающийся список.|  
||Элемент управления <xref:System.Windows.Forms.DomainUpDown>|Отображает список текстовых элементов, который можно прокручивать с помощью кнопок со стрелками вверх и вниз.|  
||Элемент управления <xref:System.Windows.Forms.ListBox>|Отображает список текстовых и графических элементов \(значков\).|  
||Элемент управления <xref:System.Windows.Forms.ListView>|Отображает элементы в одном из четырех представлений:  только текст, текст с маленькими значками, текст с большими значками и сведения.|  
||Элемент управления <xref:System.Windows.Forms.NumericUpDown>|Отображает список чисел, который можно прокручивать с помощью кнопок со стрелками вверх и вниз.|  
||Элемент управления <xref:System.Windows.Forms.TreeView>|Отображает иерархическую коллекцию объектов с узлами, которые могут включать текст, а также флажки и значки.|  
|Отображение графики|Элемент управления <xref:System.Windows.Forms.PictureBox>|Отображает во фрейме графические файлы, например растровые рисунки или значки.|  
|Хранение графики|Элемент управления <xref:System.Windows.Forms.ImageList>|Служит в качестве хранилища рисунков.  Элементы управления <xref:System.Windows.Forms.ImageList> и хранящиеся в них рисунки могут повторно использоваться в других приложениях.|  
|Установка значений|Элемент управления <xref:System.Windows.Forms.CheckBox>|Отображает флажок и надпись для текста.  В основном используется для задания параметров.|  
||Элемент управления <xref:System.Windows.Forms.CheckedListBox>|Отображает список с полосой прокрутки, состоящий из элементов с флажками.|  
||Элемент управления <xref:System.Windows.Forms.RadioButton>|Отображает кнопку, которая может быть включена или выключена.|  
||Элемент управления <xref:System.Windows.Forms.TrackBar>|Позволяет задавать значения на шкале, перемещая по ней ползунок.|  
|Установка даты|Элемент управления <xref:System.Windows.Forms.DateTimePicker>|Отображает графический календарь, позволяющий пользователю выбрать дату или время.|  
||Элемент управления <xref:System.Windows.Forms.MonthCalendar>|Отображает графический календарь, позволяющий пользователю выбрать диапазон дат.|  
|Диалоговые окна|Элемент управления <xref:System.Windows.Forms.ColorDialog>|Отображает диалоговое окно выбора цвета, позволяющее задать цвет элемента интерфейса.|  
||Элемент управления <xref:System.Windows.Forms.FontDialog>|Отображает диалоговое окно, где можно указать шрифт и его атрибуты.|  
||Элемент управления <xref:System.Windows.Forms.OpenFileDialog>|Отображает диалоговое окно для поиска и выбора файла.|  
||Элемент управления <xref:System.Windows.Forms.PrintDialog>|Отображает диалоговое окно для выбора принтера и задания его атрибутов.|  
||Элемент управления <xref:System.Windows.Forms.PrintPreviewDialog>|Отображает диалоговое окно, показывающее, как будет выглядеть напечатанный компонент элемента управления <xref:System.Drawing.Printing.PrintDocument>.|  
||Элемент управления <xref:System.Windows.Forms.FolderBrowserDialog>|Отображает диалоговое окно для поиска, создания и выбора папки.|  
||Элемент управления <xref:System.Windows.Forms.SaveFileDialog>|Отображает диалоговое окно для сохранения файла.|  
|Элементы управления меню|Элемент управления <xref:System.Windows.Forms.MenuStrip>|Создание настраиваемых меню. **Note:**  Элемент управления<xref:System.Windows.Forms.MenuStrip> предназначен для замены элемента управления <xref:System.Windows.Forms.MainMenu>.|  
||Элемент управления <xref:System.Windows.Forms.ContextMenuStrip>|Создание настраиваемых контекстных меню. **Note:**  Элемент управления<xref:System.Windows.Forms.ContextMenuStrip> предназначен для замены элемента управления <xref:System.Windows.Forms.ContextMenu>.|  
|Команды|Элемент управления <xref:System.Windows.Forms.Button>|Используется для запуска, остановки или прерывания процесса.|  
||Элемент управления <xref:System.Windows.Forms.LinkLabel>|Отображает текст в виде веб\-ссылки и создает событие при щелчке текста.  Как правило, текст является ссылкой на другое окно или на веб\-узел.|  
||Элемент управления <xref:System.Windows.Forms.NotifyIcon>|Отображает значок в области уведомлений панели задач, соответствующий приложению, выполняемому в фоновом режиме.|  
||Элемент управления <xref:System.Windows.Forms.ToolStrip>|Создает панели инструментов с использованием стилей и принципов работы Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer или других, с темами или без тем, с поддержкой переполнения и переупорядочения элементов во время выполнения. **Note:**  Элемент управления<xref:System.Windows.Forms.ToolStrip> предназначен для замены элемента управления <xref:System.Windows.Forms.ToolBar>.|  
|Пользовательская справка|Компонент <xref:System.Windows.Forms.HelpProvider>|Предоставляет всплывающие подсказки или встроенную справку для элементов управления.|  
||Компонент <xref:System.Windows.Forms.ToolTip>|При наведении указателя мыши на элемент управления предоставляет всплывающее окно с коротким описанием назначения элемента управления.|  
|Группировка других элементов управления|Элемент управления <xref:System.Windows.Forms.Panel>|Группирует набор элементов управления в прокручиваемый фрейм без подписи.|  
||Элемент управления <xref:System.Windows.Forms.GroupBox>|Группирует набор элементов управления \(например, переключателей\) в непрокручиваемый фрейм с подписью.|  
||Элемент управления <xref:System.Windows.Forms.TabControl>|Страница с вкладками для эффективной организации доступа к сгруппированным объектам.|  
||Элемент управления <xref:System.Windows.Forms.SplitContainer>|Представление двух областей, разделенных перемещаемой полосой. **Note:**  Элемент управления<xref:System.Windows.Forms.SplitContainer> предназначен для замены элемента управления <xref:System.Windows.Forms.Splitter>.|  
||Элемент управления <xref:System.Windows.Forms.TableLayoutPanel>|Представляет область, в которой содержимое динамически отображается в таблице, состоящей из строк и столбцов.|  
||Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel>|Представляет область, в которой содержимое динамически отображается вертикально или горизонтально.|  
|Звук|Элемент управления <xref:System.Media.SoundPlayer>|Воспроизводит звук в формате WAV.  Звуки можно загружать и воспроизводить асинхронно.|  
  
## Устаревшие элементы управления и компоненты по функциям  
  
|Функция|Устаревший элемент управления|Рекомендуемая замена|  
|-------------|-----------------------------------|--------------------------|  
|Отображение данных|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Отображение информации \(только для чтения\)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Элементы управления меню|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Команды|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Макет формы|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## См. также  
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)