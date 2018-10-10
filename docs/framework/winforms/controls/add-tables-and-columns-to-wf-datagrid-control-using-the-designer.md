---
title: Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: b2e8f962ed7fb9d205a9061bdc1b32c3a2f8b0bd
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873418"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Можно отобразить данные в Windows Forms <xref:System.Windows.Forms.DataGrid> элемента управления в таблицах и столбцах, создав <xref:System.Windows.Forms.DataGridTableStyle> объектов и добавления их в <xref:System.Windows.Forms.GridTableStylesCollection> объекта, доступном через <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойство. Каждая таблица отображает содержимое таблицы данных указывается в <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство <xref:System.Windows.Forms.DataGridTableStyle>. По умолчанию стиль таблицы не определены стили столбцов будет отображать все столбцы этой таблицы данных. Можно ограничить, какие столбцы из таблицы должны отображаться, добавив <xref:System.Windows.Forms.DataGridColumnStyle> объектов <xref:System.Windows.Forms.GridColumnStylesCollection>, которой осуществляется через <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> свойства каждого <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Следующие процедуры требуют **приложения Windows** проект с формой, содержащей <xref:System.Windows.Forms.DataGrid> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). По умолчанию в Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> элемент управления отсутствует в **элементов**. Сведения о его добавлении см. в разделе [как: Добавление элементов на панель инструментов](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Чтобы добавить таблицу в элемент управления DataGrid в конструкторе  
  
1.  Для отображения данных в таблице, необходимо сначала привязать <xref:System.Windows.Forms.DataGrid> элемента управления к набору данных. Дополнительные сведения см. в разделе [как: привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Выберите <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойства в окне «Свойства» и затем нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем свойство отображения **редактор коллекции DataGridTableStyle**.  
  
3.  В редакторе коллекции щелкните **добавить** Вставляемый стиль таблицы.  
  
4.  Нажмите кнопку **ОК** чтобы закрыть редактор коллекции, а затем повторно открыть его, нажав кнопку с многоточием рядом с полем <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойство.  
  
     При повторном открытии редактора коллекции, все таблицы данных, привязанных к элементу управления будет отображаться в раскрывающемся списке для <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство стиля таблицы.  
  
5.  В **члены** окно редактора коллекции, выберите стиль таблицы.  
  
6.  В **свойства** редактора коллекции, выберите <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> значение для таблицы будет отображаться.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Чтобы добавить столбец в элемент управления DataGrid в конструкторе  
  
1.  В **члены** поле **редактор коллекции DataGridTableStyle**, выберите требуемый стиль таблицы. В **свойства** редактора коллекции, выберите <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> коллекции, а затем нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) рядом со свойством для отображения **редактор коллекции DataGridColumnStyle**.  
  
2.  В редакторе коллекции щелкните **добавить** для вставки стиль столбца или щелкните стрелку вниз рядом с полем **добавить** для указания типа столбца.  
  
     В раскрывающемся списке можно выбрать либо <xref:System.Windows.Forms.DataGridTextBoxColumn> или <xref:System.Windows.Forms.DataGridBoolColumn> типа.  
  
3.  Нажмите кнопку ОК, чтобы закрыть **редактор коллекции DataGridColumnStyle**, а затем повторно открыть его, нажав кнопку с многоточием рядом с полем <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> свойство.  
  
     При повторном открытии редактора коллекции, все столбцы данных в связанной таблице данных будет отображаться в раскрывающемся списке для <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> свойство стиля столбца.  
  
4.  В **члены** окно редактора коллекции, выберите стиль столбца.  
  
5.  В **свойства** редактора коллекции, выберите <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> значение для столбца, который вы хотите отобразить.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
