---
title: Удаление или скрытие столбцов в элементе управления DataGrid
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
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743294"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Можно программно удалить или скрыть столбцы в элементе управления Windows Forms <xref:System.Windows.Forms.DataGrid> с помощью свойств и методов объектов <xref:System.Windows.Forms.GridColumnStylesCollection> и <xref:System.Windows.Forms.DataGridColumnStyle> (которые являются членами класса <xref:System.Windows.Forms.DataGridTableStyle>).  
  
 Удаленные или скрытые столбцы по-прежнему существуют в источнике данных, к которому привязана сетка, и по-прежнему доступны программно. Они больше не отображаются в DataGrid.  
  
> [!NOTE]
> Если приложение не имеет доступа к определенным столбцам данных и вы не хотите, чтобы они отображались в DataGrid, то, возможно, не нужно включать их в источник данных в первую очередь.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Программное удаление столбца из DataGrid  
  
1. В области объявления формы объявите новый экземпляр класса <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2. Задайте для свойства <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> таблицу в источнике данных, к которому необходимо применить стиль. В следующем примере используется свойство <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, которое оно предполагается, уже задано.  
  
3. Добавьте новый объект <xref:System.Windows.Forms.DataGridTableStyle> в коллекцию стилей таблиц DataGrid.  
  
4. Вызовите метод <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> коллекции <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> <xref:System.Windows.Forms.DataGrid>, указав индекс столбца, который нужно удалить.  
  
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
  
1. В области объявления формы объявите новый экземпляр класса <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2. Задайте для свойства <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> <xref:System.Windows.Forms.DataGridTableStyle> таблицу в источнике данных, к которой необходимо применить стиль. В следующем примере кода используется свойство <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, которое оно предполагается, уже задано.  
  
3. Добавьте новый объект <xref:System.Windows.Forms.DataGridTableStyle> в коллекцию стилей таблиц DataGrid.  
  
4. Скройте столбец, задав свойству `Width` значение 0, указав индекс столбца, который нужно скрыть.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
