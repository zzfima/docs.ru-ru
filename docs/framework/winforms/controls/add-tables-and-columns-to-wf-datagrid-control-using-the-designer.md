---
title: Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: d11c4f7e4cdfb597477bb99f38612ed648849f20
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040042"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Данные можно отображать в элементах управления <xref:System.Windows.Forms.DataGrid> Windows Forms в таблицах и столбцах <xref:System.Windows.Forms.DataGridTableStyle> , создавая объекты <xref:System.Windows.Forms.GridTableStylesCollection> и добавляя их к объекту <xref:System.Windows.Forms.DataGrid.TableStyles%2A> , доступ к которому <xref:System.Windows.Forms.DataGrid> осуществляется через свойство элемента управления. Каждый стиль таблицы отображает содержимое любой таблицы данных, указанной в <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойстве <xref:System.Windows.Forms.DataGridTableStyle>объекта. По умолчанию стиль таблицы без заданных стилей столбцов будет отображать все столбцы в этой таблице данных. Можно ограничить <xref:System.Windows.Forms.DataGridColumnStyle> список отображаемых столбцов таблицы, добавив объекты <xref:System.Windows.Forms.GridColumnStylesCollection>в коллекцию, доступ к <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> которой осуществляется через свойство каждого из них <xref:System.Windows.Forms.DataGridTableStyle>.

Для следующих процедур требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGrid> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms. По умолчанию в Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> элемент управления не находится на **панели элементов**. Дополнительные сведения о добавлении см. в [разделе как Добавление элементов на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Добавление таблицы в элемент управления DataGrid в конструкторе

1. Чтобы отобразить данные в таблице, необходимо сначала привязать <xref:System.Windows.Forms.DataGrid> элемент управления к набору данных. Дополнительные сведения см. в разделе [Практическое руководство. Привязка Windows Forms элемента управления DataGrid к источнику данных с помощью конструктора](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).

2. ![](./media/visual-studio-ellipsis-button.png)Выберите свойство <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGrid.TableStyles%2A> элемента управления в окно свойств, а затем нажмите кнопку с многоточием (...) в окно свойств Visual Studio.) рядом со свойством, чтобы отобразить **Редактор коллекции DataGridTableStyle**.

3. В редакторе коллекции нажмите кнопку **Добавить** , чтобы вставить стиль таблицы.

4. Нажмите кнопку **ОК** , чтобы закрыть редактор коллекции, а затем снова откройте его, нажав кнопку с многоточием рядом со <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойством.

     При повторном открытии редактора коллекции все таблицы данных, привязанные к элементу управления, будут отображаться в раскрывающемся списке для <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойства стиля таблицы.

5. В поле **члены** редактора коллекции выберите стиль таблицы.

6. В диалоговом окне **Свойства** редактора коллекции выберите <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> значение для таблицы, которую необходимо отобразить.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Добавление столбца в элемент управления DataGrid в конструкторе

1. В поле **члены** **редактора коллекции DataGridTableStyle**выберите соответствующий стиль таблицы. В диалоговом окне **Свойства** редактора коллекции выберите <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> коллекцию, а затем нажмите кнопку![с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством, чтобы отобразить **Редактор коллекции DataGridColumnStyle**.

2. В редакторе коллекции нажмите кнопку **Добавить** , чтобы вставить стиль столбца, или щелкните стрелку вниз рядом с пунктом **Добавить** , чтобы указать тип столбца.

     В раскрывающемся списке можно выбрать <xref:System.Windows.Forms.DataGridTextBoxColumn> тип или. <xref:System.Windows.Forms.DataGridBoolColumn>

3. Нажмите кнопку ОК, чтобы закрыть **Редактор коллекции DataGridColumnStyle**, а затем снова откройте его, нажав кнопку с многоточием рядом <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> со свойством.

     При повторном открытии редактора коллекции все столбцы данных в связанных таблицах данных будут отображаться в раскрывающемся списке для <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> свойства стиля столбца.

4. В поле **члены** редактора коллекции щелкните стиль столбца.

5. В диалоговом окне **Свойства** редактора коллекции выберите <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> значение для столбца, который необходимо отобразить.

## <a name="see-also"></a>См. также

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Практическое руководство. Удаление или скрытие столбцов в элементе управления Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
