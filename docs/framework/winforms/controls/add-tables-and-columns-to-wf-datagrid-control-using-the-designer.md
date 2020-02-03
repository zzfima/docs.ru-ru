---
title: Добавление таблиц и столбцов в элемент управления DataGrid с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: fed7465fbe665b1945161653616e3a21640e0b2a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746264"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Данные можно отображать в Windows Forms элементе управления <xref:System.Windows.Forms.DataGrid> в таблицах и столбцах, создавая объекты <xref:System.Windows.Forms.DataGridTableStyle> и добавляя их к объекту <xref:System.Windows.Forms.GridTableStylesCollection>, доступ к которому осуществляется через свойство <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.TableStyles%2A>. Каждый стиль таблицы отображает содержимое любой таблицы данных, указанной в свойстве <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> <xref:System.Windows.Forms.DataGridTableStyle>. По умолчанию стиль таблицы без заданных стилей столбцов будет отображать все столбцы в этой таблице данных. Чтобы ограничить отображаемые столбцы из таблицы, добавьте <xref:System.Windows.Forms.DataGridColumnStyle> объекты в <xref:System.Windows.Forms.GridColumnStylesCollection>, доступ к которым осуществляется через свойство <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> каждого <xref:System.Windows.Forms.DataGridTableStyle>.

Для следующих процедур требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGrid>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md). По умолчанию в Visual Studio 2005 элемент управления <xref:System.Windows.Forms.DataGrid> не находится на **панели элементов**. Дополнительные сведения о добавлении элементов см. в разделе [как добавить элементы на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Добавление таблицы в элемент управления DataGrid в конструкторе

1. Чтобы отобразить данные в таблице, необходимо сначала привязать элемент управления <xref:System.Windows.Forms.DataGrid> к набору данных. Дополнительные сведения см. в разделе [руководство. привязка Windows Forms элемента управления DataGrid к источнику данных с помощью конструктора](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).

2. Выберите свойство <xref:System.Windows.Forms.DataGrid.TableStyles%2A> элемента управления <xref:System.Windows.Forms.DataGrid> в окно свойств, а затем нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством, чтобы открыть **Редактор коллекции DataGridTableStyle**.

3. В редакторе коллекции нажмите кнопку **Добавить** , чтобы вставить стиль таблицы.

4. Нажмите кнопку **ОК** , чтобы закрыть редактор коллекции, а затем снова откройте его, нажав кнопку с многоточием рядом со свойством <xref:System.Windows.Forms.DataGrid.TableStyles%2A>.

     При повторном открытии редактора коллекции все таблицы данных, привязанные к элементу управления, будут отображаться в раскрывающемся списке для свойства <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> стиля таблицы.

5. В поле **члены** редактора коллекции выберите стиль таблицы.

6. В диалоговом окне **Свойства** редактора коллекции выберите <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> значение для таблицы, которую требуется отобразить.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Добавление столбца в элемент управления DataGrid в конструкторе

1. В поле **члены** **редактора коллекции DataGridTableStyle**выберите соответствующий стиль таблицы. В диалоговом окне **Свойства** редактора коллекции выберите коллекцию <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>, а затем нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством, чтобы отобразить **Редактор коллекции DataGridColumnStyle**.

2. В редакторе коллекции нажмите кнопку **Добавить** , чтобы вставить стиль столбца, или щелкните стрелку вниз рядом с пунктом **Добавить** , чтобы указать тип столбца.

     В раскрывающемся списке можно выбрать тип <xref:System.Windows.Forms.DataGridTextBoxColumn> или <xref:System.Windows.Forms.DataGridBoolColumn>.

3. Нажмите кнопку ОК, чтобы закрыть **Редактор коллекции DataGridColumnStyle**, а затем снова откройте его, нажав кнопку с многоточием рядом со свойством <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.

     При повторном открытии редактора коллекции все столбцы данных в связанных таблицах данных будут отображаться в раскрывающемся списке для свойства <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> стиля столбца.

4. В поле **члены** редактора коллекции щелкните стиль столбца.

5. В диалоговом окне **Свойства** редактора коллекции выберите <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> значение для столбца, который необходимо отобразить.

## <a name="see-also"></a>См. также раздел

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
