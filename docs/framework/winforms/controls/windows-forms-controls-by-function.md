---
title: "Функциональная классификация элементов управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c49c42b02511fea66c88544bf689b2b05e788ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-controls-by-function"></a>Функциональная классификация элементов управления Windows Forms
В Windows Forms существуют элементы управления и компоненты, которые выполняют ряд функций. В следующей таблице перечислены элементы управления Windows Forms и компонентов в соответствии с основной функцией. Кроме того где находятся несколько элементов управления, которые выполняют одинаковую функцию, рекомендуемые элементы управления перечислены с указанием использовавшихся ранее устаревших элемента управления. В отдельной таблице с их рекомендуемые замены перечислены устаревшие элементы управления.  
  
> [!NOTE]
>  Следующие таблицы не указывайте каждый элемент управления или компонент, который можно использовать в Windows Forms; более полный список см. в разделе [элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Рекомендуемые элементы управления и компоненты по функциям  
  
|Функция|Control|Описание|  
|--------------|-------------|-----------------|  
|Отображение данных|Элемент управления <xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Forms.DataGridView> Управления предоставляет настраиваемую таблицу для отображения данных. <xref:System.Windows.Forms.DataGridView> Класс позволяет настраивать ячеек, строк, столбцов и границ. **Примечание:** <xref:System.Windows.Forms.DataGridView> управления предоставляет множество основных и дополнительных компонентов, отсутствующих в <xref:System.Windows.Forms.DataGrid> элемента управления. Дополнительные сведения см. в разделе [различия между Windows Forms DataGridView и элементам управления DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Привязка данных и перемещение|<xref:System.Windows.Forms.BindingSource>компонент|Упрощает привязку элементов управления в форме к данным за счет управления, уведомления об изменениях и другие службы.|  
||Элемент управления <xref:System.Windows.Forms.BindingNavigator>|Предоставляет интерфейс для работы с данными в форме тип панели инструментов.|  
|Редактирование текста|Элемент управления <xref:System.Windows.Forms.TextBox>|Отображает текст, введенный на этапе разработки, который может редактироваться пользователями во время выполнения или изменить программным способом.|  
||Элемент управления <xref:System.Windows.Forms.RichTextBox>|Включает текст, который отображается в формате в обычный текст или текст в формате (RTF).|  
||Элемент управления <xref:System.Windows.Forms.MaskedTextBox>|Ограничивает формат вводимых пользователем данных|  
|Отображение информации (только для чтения)|Элемент управления <xref:System.Windows.Forms.Label>|Отображает текст, недоступный для непосредственного изменения пользователем.|  
||Элемент управления <xref:System.Windows.Forms.LinkLabel>|Отображает текст в виде веб-ссылку и вызывает событие, когда пользователь щелкает этот текст. Обычно текст является ссылкой на другое окно или веб-сайта.|  
||Элемент управления <xref:System.Windows.Forms.StatusStrip>|Отображает сведения о текущем состоянии приложения в рамках области, обычно в нижней части родительской формы.|  
||Элемент управления <xref:System.Windows.Forms.ProgressBar>|Отображает текущее состояние операции для пользователя.|  
|Отображение веб-страницы|Элемент управления <xref:System.Windows.Forms.WebBrowser>|Предоставляет пользователю возможность осуществлять навигацию по веб-страницам внутри формы.|  
|Выбор из списка|Элемент управления <xref:System.Windows.Forms.CheckedListBox>|Отображает прокручиваемый список элементов с флажками.|  
||Элемент управления <xref:System.Windows.Forms.ComboBox>|Отображает список элементов раскрывающегося списка.|  
||Элемент управления <xref:System.Windows.Forms.DomainUpDown>|Отображает список текстовых элементов, который можно прокручивать с помощью кнопок со стрелками.|  
||Элемент управления <xref:System.Windows.Forms.ListBox>|Отображает список текстовых и графических элементов (значков).|  
||Элемент управления <xref:System.Windows.Forms.ListView>|Отображает элементы в одном из четырех различных представлений. Включает в себя только текст, текст с маленькими значками, текст с большими значками и подробности.|  
||Элемент управления <xref:System.Windows.Forms.NumericUpDown>|Отображает список чисел, который можно прокручивать с помощью кнопок со стрелками.|  
||Элемент управления <xref:System.Windows.Forms.TreeView>|Отображает иерархическую структуру объектов узла, которые могут включать текст с флажки и значки.|  
|Отображение графики|Элемент управления <xref:System.Windows.Forms.PictureBox>|Отображает графические файлы, такие как растровые изображения и значки, в кадре.|  
|Хранение графики|Элемент управления <xref:System.Windows.Forms.ImageList>|Служит в качестве репозитория для изображений. <xref:System.Windows.Forms.ImageList>элементы управления и изображения, которые они содержат можно использовать повторно из одного приложения к другому.|  
|Значение параметра|Элемент управления <xref:System.Windows.Forms.CheckBox>|Отображает флажок и надпись для текста. Обычно используется для задания параметров.|  
||Элемент управления <xref:System.Windows.Forms.CheckedListBox>|Отображает прокручиваемый список элементов с флажками.|  
||Элемент управления <xref:System.Windows.Forms.RadioButton>|Отображает кнопку, которая может включать и выключать.|  
||Элемент управления <xref:System.Windows.Forms.TrackBar>|Позволяет пользователям задавать значения на шкале, перемещая «ползунок» на шкале.|  
|Настройка даты|Элемент управления <xref:System.Windows.Forms.DateTimePicker>|Отображает графический календарь, позволяющий пользователю выбрать дату или время.|  
||Элемент управления <xref:System.Windows.Forms.MonthCalendar>|Отображает графический календарь, позволяющий пользователю выбрать диапазон дат.|  
|Диалоговые окна|Элемент управления <xref:System.Windows.Forms.ColorDialog>|Отображение диалогового окна выбора цвета, которая позволяет пользователям задать цвет элемента интерфейса.|  
||Элемент управления <xref:System.Windows.Forms.FontDialog>|Отображает диалоговое окно, которое позволяет пользователям задавать шрифт и его атрибуты.|  
||Элемент управления <xref:System.Windows.Forms.OpenFileDialog>|Отображает диалоговое окно, позволяющее пользователям перейдите и выберите файл.|  
||Элемент управления <xref:System.Windows.Forms.PrintDialog>|Отображает диалоговое окно для выбора принтера и задайте его атрибуты.|  
||Элемент управления <xref:System.Windows.Forms.PrintPreviewDialog>|Отображает диалоговое окно отображает элемент управления <xref:System.Drawing.Printing.PrintDocument> компонента будет выглядеть при печати.|  
||Элемент управления <xref:System.Windows.Forms.FolderBrowserDialog>|Отображает диалоговое окно, которое позволяет пользователям для просмотра, создания и выбора папки.|  
||Элемент управления <xref:System.Windows.Forms.SaveFileDialog>|Отображает диалоговое окно для сохранения файла.|  
|Элементы управления меню|Элемент управления <xref:System.Windows.Forms.MenuStrip>|Создание настраиваемых меню. **Примечание:** <xref:System.Windows.Forms.MenuStrip> предназначена для замены <xref:System.Windows.Forms.MainMenu> элемента управления.|  
||Элемент управления <xref:System.Windows.Forms.ContextMenuStrip>|Создание настраиваемых контекстных меню. **Примечание:** <xref:System.Windows.Forms.ContextMenuStrip> предназначена для замены <xref:System.Windows.Forms.ContextMenu> элемента управления.|  
|Команды|Элемент управления <xref:System.Windows.Forms.Button>|Запускает, останавливает или прерывания процесса.|  
||Элемент управления <xref:System.Windows.Forms.LinkLabel>|Отображает текст в виде веб-ссылку и вызывает событие, когда пользователь щелкает этот текст. Обычно текст является ссылкой на другое окно или веб-сайта.|  
||Элемент управления <xref:System.Windows.Forms.NotifyIcon>|Отображает значок в области уведомлений панели задач, который представляет приложение, работающее в фоновом режиме.|  
||Элемент управления <xref:System.Windows.Forms.ToolStrip>|Создание панелей инструментов, которые могут иметь Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer или пользовательского интерфейса, с или без темы и поддержка переполнение и реорганизацию элементов во время выполнения. **Примечание:** <xref:System.Windows.Forms.ToolStrip> элемент управления предназначен для замены <xref:System.Windows.Forms.ToolBar> элемента управления.|  
|Справка по пользовательскому|<xref:System.Windows.Forms.HelpProvider>компонент|Обеспечивает для элементов управления всплывающее окно справки или окно оперативной справки.|  
||<xref:System.Windows.Forms.ToolTip>компонент|Предоставляет всплывающее окно, в котором отображается краткое описание назначения элемента управления при наведении указателя мыши на элементе управления.|  
|Группировка других элементов управления|Элемент управления <xref:System.Windows.Forms.Panel>|Группирует набор элементов управления в прокручиваемый фрейм без подписи.|  
||Элемент управления <xref:System.Windows.Forms.GroupBox>|Группирует набор элементов управления (например, переключателей) в непрокручиваемый фрейм.|  
||Элемент управления <xref:System.Windows.Forms.TabControl>|Предоставляет страницы с вкладками для организации и доступ к эффективно сгруппированных объектов.|  
||Элемент управления <xref:System.Windows.Forms.SplitContainer>|Предоставляет двух панелей, разделенных подвижной полосой. **Примечание:** <xref:System.Windows.Forms.SplitContainer> элемент управления предназначен для замены <xref:System.Windows.Forms.Splitter> элемента управления.|  
||Элемент управления <xref:System.Windows.Forms.TableLayoutPanel>|Представляет панель, в которой содержимое динамически отображается в сетке, состоящей из строк и столбцов.|  
||Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel>|Представляет панель, которая динамически располагает содержимое по горизонтали или вертикали.|  
|Звук|Элемент управления <xref:System.Media.SoundPlayer>|Воспроизводит звук в формате WAV. Звук может быть загружен или воспроизводить асинхронно.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Устаревшие элементы управления и компоненты по функциям  
  
|Функция|Устаревший элемент управления|Рекомендуется на замену|  
|--------------|------------------------|-----------------------------|  
|Отображение данных|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Отображение информации (только для чтения элементы управления)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Элементы управления меню|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Команды|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Макет формы|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>См. также  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
