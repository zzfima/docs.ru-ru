---
title: Практическое руководство. Удаление или скрытие столбцов элемента управления DataGrid в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 70229abddb831788f521f85747db1093c941ba8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967377"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Практическое руководство. Удаление или скрытие столбцов элемента управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Можно программно удалить или скрыть столбцы в элементе управления <xref:System.Windows.Forms.DataGrid> Windows Forms с помощью свойств и методов <xref:System.Windows.Forms.GridColumnStylesCollection> объектов и <xref:System.Windows.Forms.DataGridColumnStyle> (которые являются членами <xref:System.Windows.Forms.DataGridTableStyle> класса).  
  
 Удаленные или скрытые столбцы по-прежнему существуют в источнике данных, к которому привязана сетка, и по-прежнему доступны программно. Они больше не отображаются в DataGrid.  
  
> [!NOTE]
> Если приложение не имеет доступа к определенным столбцам данных и вы не хотите, чтобы они отображались в DataGrid, то, возможно, не нужно включать их в источник данных в первую очередь.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Программное удаление столбца из DataGrid  
  
1. В области объявления формы объявите новый экземпляр <xref:System.Windows.Forms.DataGridTableStyle> класса.  
  
2. Задайте для <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> свойства таблицу в источнике данных, к которой необходимо применить стиль. В следующем примере используется <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> свойство, которое предполагается, если уже задано.  
  
3. Добавьте новый <xref:System.Windows.Forms.DataGridTableStyle> объект в коллекцию стилей таблиц DataGrid.  
  
4. Вызовите <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> метод <xref:System.Windows.Forms.DataGrid> коллекции,указавиндексстолбца,<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> который нужно удалить.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>Скрытие столбца в DataGrid программным способом  
  
1. В области объявления формы объявите новый экземпляр <xref:System.Windows.Forms.DataGridTableStyle> класса.  
  
2. <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Установите свойство<xref:System.Windows.Forms.DataGridTableStyle> объекта в таблицу в источнике данных, к которому необходимо применить стиль. В следующем примере кода используется <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> свойство, которое предполагается, если уже задано.  
  
3. Добавьте новый <xref:System.Windows.Forms.DataGridTableStyle> объект в коллекцию стилей таблиц DataGrid.  
  
4. Скройте столбец, установив его `Width` свойство в значение 0, указав индекс столбца, который нужно скрыть.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Изменение отображаемых данных во время выполнения в элементе управления Windows Forms DataGrid](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления Windows Forms DataGrid](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
