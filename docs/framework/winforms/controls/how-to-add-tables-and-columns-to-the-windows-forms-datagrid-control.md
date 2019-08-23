---
title: Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms
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
ms.openlocfilehash: 55e30744f57364fb37c9fde5b6bade6bab60fa26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925089"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Данные можно отображать в элементах управления <xref:System.Windows.Forms.DataGrid> Windows Forms в таблицах и столбцах, создавая объекты **DataGridTableStyle** и добавляя их к объекту **GridTableStylesCollection** <xref:System.Windows.Forms.DataGrid> , доступ к которому осуществляется через элемент управления Свойство **TableStyles** . Каждый стиль таблицы отображает содержимое любой таблицы данных, указанной в свойстве **MappingName** объекта **DataGridTableStyle** . По умолчанию в стиле таблицы, в котором не указаны стили столбцов, отображаются все столбцы в таблице данных. Чтобы ограничить отображаемые столбцы из таблицы, добавьте объекты **DataGridColumnStyle** в объект **GridColumnStylesCollection** , доступ к которому осуществляется через свойство **GridColumnStyles** каждого элемента **DataGridTableStyle** . объектами.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Добавление таблицы и столбца в DataGrid программным способом  
  
1. Чтобы отобразить данные в таблице, необходимо сначала привязать <xref:System.Windows.Forms.DataGrid> элемент управления к набору данных. Дополнительные сведения см. в разделе [Практическое руководство. Привязка Windows Forms элемента управления DataGrid к источнику](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)данных.  
  
    > [!CAUTION]
    >  При программном указании стилей столбцов всегда создавайте объекты **DataGridColumnStyle** и добавляйте их в объект **GridColumnStylesCollection** перед добавлением объектов **DataGridTableStyle в Объект GridTableStylesCollection** . При добавлении пустого объекта **DataGridTableStyle** в коллекцию объекты **DataGridColumnStyle** создаются автоматически. Следовательно, при попытке добавить новые объекты **DataGridColumnStyle** с повторяющимися значениями **MappingName** в объект **GridColumnStylesCollection** будет создано исключение.  
  
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
  
## <a name="see-also"></a>См. также

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Практическое руководство. Удаление или скрытие столбцов в элементе управления Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
