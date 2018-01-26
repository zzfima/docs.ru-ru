---
title: "Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca34b5daff07b733ccf2bfb4269c11cff80c7549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Может отображать данные в Windows Forms <xref:System.Windows.Forms.DataGrid> управления в таблицах и столбцах, создав **DataGridTableStyle** объектов и добавления их в **GridTableStylesCollection** объекта, имеющего доступ через <xref:System.Windows.Forms.DataGrid> элемента управления **TableStyles** свойство. Каждая таблица отображается содержимое таблицы данных указывается в **DataGridTableStyle** объекта **MappingName** свойство. По умолчанию стиля таблицы стили столбцов, не указано, отображаются все столбцы в этой таблице данных. Вы можете ограничить отображаются столбцы из таблицы, добавив **DataGridColumnStyle** объектов **GridColumnStylesCollection** объект, который можно получить с помощью  **GridColumnStyles** каждого экземпляра **DataGridTableStyle** объекта.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Добавление таблиц и столбцов в элемент управления DataGrid программными средствами  
  
1.  Для отображения данных в таблице, необходимо сначала привязать <xref:System.Windows.Forms.DataGrid> элемента управления к набору данных. Дополнительные сведения см. в разделе [как: привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Указывая программно стили столбцов всегда создавать **DataGridColumnStyle** объектов и добавлять их в **GridColumnStylesCollection** объекта перед добавлением  **DataGridTableStyle** объектов **GridTableStylesCollection** объекта. При добавлении пустого **DataGridTableStyle** в коллекцию **DataGridColumnStyle** объекты создаются автоматически для вас. Следовательно, будет создано исключение при попытке добавить новый **DataGridColumnStyle** объектов с повторяющимися **MappingName** значения **GridColumnStylesCollection**объекта.  
  
2.  Объявите новый стиль таблицы и присвойте ему имя сопоставления.  
  
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
  
3.  Объявите новый стиль столбца и задайте его имя сопоставления и другие свойства.  
  
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
  
4.  Вызовите **добавить** метод **GridColumnStylesCollection** объект для добавления столбца таблицы стилей  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Вызовите **добавить** метод **GridTableStylesCollection** объект для добавления стилей таблиц сетки данных.  
  
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
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
