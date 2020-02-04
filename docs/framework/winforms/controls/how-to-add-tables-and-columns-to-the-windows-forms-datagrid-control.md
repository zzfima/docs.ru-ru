---
title: Добавление таблиц и столбцов в элемент управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747204"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Данные можно отображать в Windows Forms элементе управления <xref:System.Windows.Forms.DataGrid> в таблицах и столбцах, создавая объекты **DataGridTableStyle** и добавляя их к объекту **GridTableStylesCollection** , доступ к которому осуществляется через свойство **TableStyles** элемента управления <xref:System.Windows.Forms.DataGrid>. Каждый стиль таблицы отображает содержимое любой таблицы данных, указанной в свойстве **MappingName** объекта **DataGridTableStyle** . По умолчанию в стиле таблицы, в котором не указаны стили столбцов, отображаются все столбцы в таблице данных. Можно ограничить список отображаемых столбцов таблицы, добавив объекты **DataGridColumnStyle** в объект **GridColumnStylesCollection** , доступ к которому осуществляется через свойство **GridColumnStyles** каждого объекта **DataGridTableStyle** .

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Добавление таблицы и столбца в DataGrid программным способом

1. Чтобы отобразить данные в таблице, необходимо сначала привязать элемент управления <xref:System.Windows.Forms.DataGrid> к набору данных. Дополнительные сведения см. в разделе [руководство. привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

    > [!CAUTION]
    > При программном указании стилей столбцов всегда создавайте объекты **DataGridColumnStyle** и добавляйте их в объект **GridColumnStylesCollection** перед добавлением объектов **DataGridTableStyle** в объект **GridTableStylesCollection** . При добавлении пустого объекта **DataGridTableStyle** в коллекцию объекты **DataGridColumnStyle** создаются автоматически. Следовательно, при попытке добавить новые объекты **DataGridColumnStyle** с повторяющимися значениями **MappingName** в объект **GridColumnStylesCollection** будет создано исключение.

2. Объявите новый стиль таблицы и задайте его имя сопоставления.

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. Объявите новый стиль столбца и задайте его имя сопоставления и другие свойства.

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. Вызовите метод **Add** объекта **GridColumnStylesCollection** , чтобы добавить столбец в стиль таблицы.

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. Вызовите метод **Add** объекта **GridTableStylesCollection** , чтобы добавить стиль таблицы в сетку данных.

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a>См. также раздел

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
