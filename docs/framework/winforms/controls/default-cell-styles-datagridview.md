---
title: "Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "ячейки, установка стилей"
  - "данные [Windows Forms], установка форматов"
  - "форматы данных"
  - "DataGridView - элемент управления [Windows Forms], стили ячеек"
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора
Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет установить стили для ячейки по умолчанию и форматы данных ячейки для всего элемента управления, для определенных столбцов, для заголовков строк и столбцов, а также для чередующихся строк для создания эффекта бухгалтерской книги.  Стили по умолчанию, установленные для всего элемента управления, переопределяются стилями по умолчанию, установленными для столбцов и чередующихся строк.  Кроме того, стили, устанавливаемые для отдельных строк и ячеек, переопределяют установленные по умолчанию стили.  
  
 Дополнительные сведения о стилях ячеек см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  Сведения об установки стилей для чередующихся строк см. в разделе [Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Для установки стилей можно также использовать свойство <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>, действующее на все строки, которые будут добавлены в элемент управления.  Дополнительные сведения о шаблоне строк см. в разделе [Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Для следующих процедур требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Установка стилей по умолчанию для всех ячеек элемента управления  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.DataGridView> в конструкторе.  
  
2.  В окне **Свойства** нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.  Откроется диалоговое окно **Построитель стилей ячеек**.  
  
3.  Определите стиль путем установки свойств, используя панель **Предварительный просмотр** для подтверждения выбранных настроек.  
  
> [!NOTE]
>  Если визуальные стили включены, то стили заголовков строк и столбцов \(кроме <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>\) автоматически определяются текущей темой, переопределяя значения свойств <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.  
>   
>  С помощью конструктора можно установить стили ячеек для нескольких выбранных элементов управления <xref:System.Windows.Forms.DataGridView>, но только в том случае, если они имеют одинаковые значения изменяемого свойства стилей ячеек.  Если это свойство в каких\-либо стилях ячеек отличается, то окна **Свойства** диалогового окна **Построитель стилей ячеек** будут пустыми.  
  
### Установка стилей по умолчанию для ячеек отдельных столбцов  
  
1.  Щелкните правой кнопкой мыши по элементу управления <xref:System.Windows.Forms.DataGridView> в конструкторе и выберите команду **Правка столбцов**.  
  
2.  Выберите столбец из списка **Выбранные столбцы**.  
  
3.  В таблице **Свойства столбца** нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>.  Откроется диалоговое окно **Построитель стилей ячеек**.  
  
4.  Определите стиль путем установки свойств, используя панель **Предварительный просмотр** для подтверждения выбранных настроек.  
  
### Форматирование данных в ячейках  
  
1.  Воспользуйтесь одной из предыдущих процедур для отображения диалогового окна **Построитель стилей ячеек**, связанного со свойством стиля ячейки по умолчанию.  
  
2.  В диалоговом окне **Построитель стилей ячеек** нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>.  Отобразится диалоговое окно **Строка формата**.  
  
3.  Выберите тип формата, затем измените детали типа \(например количество отображаемых десятичных знаков\), используя поле **Образец** для подтверждения выбранных настроек.  
  
4.  В случае привязки элемента управления <xref:System.Windows.Forms.DataGridView> к источнику данных, который может содержать значения NULL, заполните текстовое поле **Значение NULL**.  Это значение будет отображаться при значении ячейки, равном пустой ссылке \(NULL\) \(`Nothing` в Visual Basic\) или <xref:System.DBNull.Value?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=fullName>   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)