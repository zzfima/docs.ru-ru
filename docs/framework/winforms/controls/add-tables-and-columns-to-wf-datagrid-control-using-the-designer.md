---
title: Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 4b29a3040415cce8fad27abf9bf46aa3d3e14b4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Может отображать данные в Windows Forms <xref:System.Windows.Forms.DataGrid> управления в таблицах и столбцах, создав <xref:System.Windows.Forms.DataGridTableStyle> объектов и добавления их в <xref:System.Windows.Forms.GridTableStylesCollection> объект, который можно получить с помощью <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойство. Каждая таблица отображается содержимое таблицы данных указывается в <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство <xref:System.Windows.Forms.DataGridTableStyle>. По умолчанию стиль таблицы не определены стили столбцов отображаются все столбцы в этой таблице данных. Вы можете ограничить отображаются столбцы из таблицы, добавив <xref:System.Windows.Forms.DataGridColumnStyle> объектов <xref:System.Windows.Forms.GridColumnStylesCollection>, которой осуществляется с помощью <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> каждого экземпляра <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Следующие процедуры требуют **приложение Windows** проект с формой, содержащей <xref:System.Windows.Forms.DataGrid> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). По умолчанию в [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> управления не находится в **элементов**. Сведения о его добавлении см. в разделе [как: Добавление элементов в область элементов](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Добавление таблицы к элементу управления DataGrid в конструкторе  
  
1.  Для отображения данных в таблице, необходимо сначала привязать <xref:System.Windows.Forms.DataGrid> элемента управления к набору данных. Дополнительные сведения см. в разделе [как: привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Выберите <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.TableStyles%2A> в окне свойств, а затем нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с свойство для отображения **редактор коллекции DataGridTableStyle**.  
  
3.  В редакторе коллекции выберите **добавить** для добавления стиля таблицы.  
  
4.  Нажмите кнопку **ОК** закройте редактор коллекции и затем снова открыть его, нажав кнопку с многоточием рядом с <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойство.  
  
     При повторном открытии редактора коллекции, все таблицы данных, привязанных к элементу управления будет отображаться в раскрывающемся списке для <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойства стиля таблицы.  
  
5.  В **члены** окно редактора коллекции выберите стиль таблицы.  
  
6.  В **свойства** редактора коллекции, выберите <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> значение для таблицы, которые требуется отобразить.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Чтобы добавить столбец в элемент управления DataGrid в конструкторе  
  
1.  В **элементы** поле **редактор коллекции DataGridTableStyle**, выберите требуемый стиль таблицы. В **свойства** редактора коллекции, выберите <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> коллекции, а затем нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) рядом со свойством, чтобы открыть **редактор коллекции DataGridColumnStyle**.  
  
2.  В редакторе коллекции выберите **добавить** вставить стиль столбца, или нажмите стрелку вниз рядом с **добавить** для указания типа столбца.  
  
     В раскрывающемся списке можно выбрать <xref:System.Windows.Forms.DataGridTextBoxColumn> или <xref:System.Windows.Forms.DataGridBoolColumn> типа.  
  
3.  Нажмите кнопку ОК, чтобы закрыть **редактор коллекции DataGridColumnStyle**, а затем снова открыть его, нажав кнопку с многоточием рядом с <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> свойство.  
  
     При повторном открытии редактора коллекции все столбцы данных в связанной таблице данных будет отображаться в раскрывающемся списке для <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> свойства стиля столбца.  
  
4.  В **члены** окно редактора коллекции выберите стиль столбца.  
  
5.  В **свойства** редактора коллекции, выберите <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> значение для столбца, который необходимо отобразить.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
