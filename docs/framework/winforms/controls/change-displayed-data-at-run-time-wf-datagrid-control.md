---
title: Изменение отображаемых данных во время выполнения в элементе управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: f91e2ea01ef4a52dd649efed70319017efb8368a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740589"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 После создания Windows Forms <xref:System.Windows.Forms.DataGrid> с помощью функций времени разработки, может также потребоваться динамическое изменение элементов <xref:System.Data.DataSet> объекта Grid во время выполнения. Это может быть изменение либо отдельных значений таблицы, либо изменением источника данных, привязанного к элементу управления <xref:System.Windows.Forms.DataGrid>. Изменения отдельных значений выполняются с помощью объекта <xref:System.Data.DataSet>, а не <xref:System.Windows.Forms.DataGrid> элемента управления.  
  
### <a name="to-change-data-programmatically"></a>Программное изменение данных  
  
1. Укажите нужную таблицу из объекта <xref:System.Data.DataSet>, а также нужную строку и поле из таблицы и установите ячейку, равную новому значению.  
  
    > [!NOTE]
    > Чтобы указать первую таблицу <xref:System.Data.DataSet> или первую строку таблицы, используйте значение 0.  
  
     В следующем примере показано, как изменить вторую запись первой строки первой таблицы набора данных, нажав кнопку `Button1`. Ранее были созданы <xref:System.Data.DataSet> (`ds`) и таблицы (`0` и `1`).  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Во время выполнения можно использовать метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> для привязки элемента управления <xref:System.Windows.Forms.DataGrid> к другому источнику данных. Например, у вас может быть несколько элементов управления данными ADO.NET, каждый из которых подключен к другой базе данных.  
  
### <a name="to-change-the-datasource-programmatically"></a>Изменение источника данных программным способом  
  
1. Задайте методу <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> имя источника данных и таблицы, к которым необходимо выполнить привязку.  
  
     В следующем примере показано, как изменить источник даты с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> к элементу управления данными ADO.NET (Адопубсаусорс), который подключен к таблице authors в базе данных Pubs.  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a>См. также:

- [DataSets в ADO.NET](../../data/adonet/ado-net-datasets.md)
- [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
