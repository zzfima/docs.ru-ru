---
title: "Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], добавление данных к элементу управления DataGrid"
  - "DataGrid - элемент управления [Windows Forms], добавление таблиц и столбцов"
  - "таблицы [Windows Forms], добавление данных к элементу управления DataGrid"
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Данные в элементе управления Windows Forms <xref:System.Windows.Forms.DataGrid> можно отображать в таблицах и столбцах, создавая объекты **DataGridTableStyle** и добавляя их в объект **GridTableStylesCollection**, к которому можно получить доступ через свойство **TableStyles** элемента управления <xref:System.Windows.Forms.DataGrid>.  Каждый стиль таблицы позволяет отображать содержимое таблицы данных, указанной в свойстве **MappingName** объекта **DataGridTableStyle**.  При использовании стиля таблицы, в котором не определены стили столбцов, по умолчанию отображаются все столбцы таблицы данных.  Можно ограничить число отображаемых столбцов, добавив объекты **DataGridColumnStyle** в объект **GridColumnStylesCollection**, доступ к которому можно получить с помощью свойства **GridColumnStyles** любого объекта **DataGridTableStyle**.  
  
### Чтобы добавить таблицу и столбец в элемент управления DataGrid программными средствами  
  
1.  Чтобы представить данные в таблице, необходимо сначала привязать элемент управления <xref:System.Windows.Forms.DataGrid> к набору данных.  Дополнительные сведения см. в разделе [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  При программном определении стилей столбцов всегда создавайте объекты **DataGridColumnStyle** и добавляйте их в объект **GridColumnStylesCollection** перед добавлением объектов **DataGridTableStyle** в объект **GridTableStylesCollection**.  При добавлении в коллекцию пустого объекта **DataGridTableStyle** автоматически создаются объекты **DataGridColumnStyle**.  Следовательно, при попытке добавления новых объектов **DataGridColumnStyle** с существующими значениями **MappingName** в объекте **GridColumnStylesCollection** возникнет исключение.  
  
2.  Объявите новый стиль таблицы и укажите для нее имя сопоставления.  
  
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
  
3.  Объявите новый стиль столбца и задайте его имя сопоставления, а также другие свойства.  
  
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
  
4.  Вызовите метод **Add** объекта **GridColumnStylesCollection** для добавления столбца в стиль таблицы.  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Вызовите метод **Add** объекта **GridTableStylesCollection** для добавления стиля таблицы в сетку данных.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)