---
title: "Практическое руководство. Форматирование элемента управления DataGrid в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "цвета, применение к элементам управления DataGrid"
  - "столбцы [Windows Forms], DataGrid - элементы управления"
  - "DataGrid - элемент управления [Windows Forms], основные стили"
  - "DataGrid - элемент управления [Windows Forms], форматирование"
  - "форматирование [Windows Forms]"
  - "таблицы [Windows Forms], форматирование данных в элементе управления DataGrid"
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Форматирование элемента управления DataGrid в формах Windows Forms с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Выделение разными цветами различных частей элемента управления <xref:System.Windows.Forms.DataGrid> поможет облегчить чтение и понимание сведений.  Цветами можно выделять строки и столбцы.  Строки и столбцы можно также скрывать или отображать по необходимости.  
  
 Форматирование элемента управления <xref:System.Windows.Forms.DataGrid> состоит из трех основных этапов.  
  
-   Можно настроить свойства для создания стиля отображения данных по умолчанию.  
  
-   На этой основе можно затем изменить способ представления определенных таблиц во время выполнения.  
  
-   Наконец, можно указать столбцы, отображаемые в сетке данных, а также цвета и другие параметры форматирования для них.  
  
 На первом этапе форматирования сетки данных можно задать свойства элемента управления <xref:System.Windows.Forms.DataGrid>.  Выбранные параметры цветов и форматирования составляют основу, в которую впоследствии можно вносить изменения, исходя из требований к отображению таблиц и столбцов.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGrid>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится в **панели элементов**.  Дополнительные сведения см. в разделе [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ru-ru/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать стиль по умолчанию для элемента управления DataGrid  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.DataGrid>.  
  
2.  В окне **Свойства** установите следующие свойства нужным образом.  
  
    |Свойство.|Описание|  
    |---------------|--------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Свойство `BackColor` определяет цвет четных строк сетки.  Если в свойстве <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> задан другой цвет, все остальные строки выделяются этим цветом \(строки 1, 3, 5 и так далее\).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Фоновый цвет четных строк сетки \(строки 0, 2, 4, 6 и так далее\).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Если свойства <xref:System.Windows.Forms.DataGrid.BackColor%2A> и <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> определяют цвета строк сетки, то свойство <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> определяет цвет области, незанятой строками, которая видна, только когда сетка прокручена вниз или содержит небольшое количество строк.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Стиль границы сетки — одно из перечисляемых значений свойства <xref:System.Windows.Forms.BorderStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Фоновый цвет заголовка окна сетки, расположенного непосредственно над сеткой.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Шрифт заголовка в верхней части сетки.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Фоновый цвет заголовка окна сетки.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Шрифт текста в сетке.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Цвет шрифта, которым представлены данные в строках сетки.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Цвет линий сетки.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Стиль линий, разделяющих ячейки сетки — одно из перечисляемых значений свойства <xref:System.Windows.Forms.DataGridLineStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Фоновый цвет заголовков строк и столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Шрифт заголовков столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Цвет заголовков столбцов сетки, включая текст самих заголовков, а также знаки плюс \(\+\) и минус \(\-\), служащие для развертывания и свертывания строк при просмотре нескольких связанных таблиц.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Цвет текста всех ссылок в сетке данных, включая ссылки на дочерние таблицы, имя отношения и так далее.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|Фоновый цвет родительских строк в дочерней таблице.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|Цвет текста родительских строк в дочерней таблице.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Определяет, отображаются ли названия таблицы и столбцов в родительской строке с помощью перечисления <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Стандартная ширина \(в пикселях\) столбцов сетки.  Установите это свойство, прежде чем сбрасывать свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> \(либо отдельно, либо с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\), иначе свойство не подействует.<br /><br /> Данное свойство не может иметь отрицательное значение.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Стандартная высота \(в пикселях\) строк сетки.  Установите это свойство, прежде чем сбрасывать свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> \(либо отдельно, либо с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\), иначе свойство не подействует.<br /><br /> Данное свойство не может иметь отрицательное значение.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ширина заголовков строк сетки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Фоновый цвет выделенной строки или ячейки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Цвет текста выделенной строки или ячейки.|  
  
    > [!NOTE]
    >  При настройке цветов элементов управления следует учесть, что выбор неудачных цветов \(например, красный и зеленый\) может затруднить работу с элементом управления.  Чтобы избежать этого, используйте цвета из палитры **Системные цвета**.  
  
     Для следующей процедуры требуется элемент управления <xref:System.Windows.Forms.DataGrid>, связанный с таблицей данных.  Дополнительные сведения см. в разделе [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### Чтобы задать стили таблицы и столбца таблицы данных во время проектирования  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.DataGrid> в форме.  
  
2.  В окне **Свойства** выберите свойство <xref:System.Windows.Forms.DataGrid.TableStyles%2A> и нажмите кнопку с **Многоточием** \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством.  
  
3.  В окне **Редактор коллекции DataGridTableStyle** нажмите кнопку **Добавить**, чтобы добавить к коллекции стиль таблицы.  
  
     В диалоговом окне **Редактор коллекции DataGridTableStyle** можно добавлять и удалять стили таблиц, задавать свойства отображения и расположения, а также указывать имена сопоставления для стилей таблиц.  
  
4.  Укажите в свойстве <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> имя сопоставления для каждого стиля таблицы.  
  
     Имя сопоставления задает стиль таблицы.  
  
5.  В окне **Редактор коллекции DataGridTableStyle** выберите свойство <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> и нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\).  
  
6.  В окне **Редактор коллекции DataGridColumnStyle** добавьте стили столбцов к созданному стилю таблицы.  
  
     В диалоговом окне **Редактор коллекции DataGridColumnStyle** можно добавлять и удалять стили столбцов, задавать свойства отображения и расположения, а также указывать имена сопоставления и строки форматирования для столбцов данных.  
  
    > [!NOTE]
    >  Дополнительные сведения о строках форматирования см. в разделе [Типы форматирования](../../../../docs/standard/base-types/formatting-types.md).  
  
## См. также  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)