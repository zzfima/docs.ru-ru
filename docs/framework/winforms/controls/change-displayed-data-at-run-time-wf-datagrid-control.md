---
title: Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms
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
ms.openlocfilehash: c7bf70a67729744f4cf96318f6b270a5ea81b812
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917728"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 После создания Windows Forms <xref:System.Windows.Forms.DataGrid> с помощью функций времени разработки может также потребоваться динамическое изменение элементов <xref:System.Data.DataSet> объекта Grid во время выполнения. Это может быть изменение либо отдельных значений таблицы, либо изменение источника данных, привязанного к <xref:System.Windows.Forms.DataGrid> элементу управления. Изменения отдельных значений выполняются через <xref:System.Data.DataSet> объект, а не в <xref:System.Windows.Forms.DataGrid> элемент управления.  
  
### <a name="to-change-data-programmatically"></a>Программное изменение данных  
  
1. Укажите нужную таблицу из <xref:System.Data.DataSet> объекта и нужную строку и поле из таблицы и установите ячейку, равную новому значению.  
  
    > [!NOTE]
    > Чтобы указать первую таблицу <xref:System.Data.DataSet> или первую строку таблицы, используйте значение 0.  
  
     В следующем примере показано, как изменить вторую запись первой строки первой таблицы набора данных, нажав кнопку `Button1`. () И`0` таблицы (и `1`) были созданы ранее.`ds` <xref:System.Data.DataSet>  
  
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
  
     Во время выполнения можно использовать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод для <xref:System.Windows.Forms.DataGrid> привязки элемента управления к другому источнику данных. Например, у вас может быть несколько элементов управления данными ADO.NET, каждый из которых подключен к другой базе данных.  
  
### <a name="to-change-the-datasource-programmatically"></a>Изменение источника данных программным способом  
  
1. <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Задайте методу имя источника данных и таблицы, к которым необходимо выполнить привязку.  
  
     В следующем примере показано, как изменить источник даты с помощью <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метода для элемента управления данными ADO.NET (адопубсаусорс), который подключен к таблице authors в базе данных Pubs.  
  
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
  
## <a name="see-also"></a>См. также

- [DataSets в ADO.NET](../../data/adonet/ado-net-datasets.md)
- [Практическое руководство. Удаление или скрытие столбцов в элементе управления Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления Windows Forms DataGrid](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Практическое руководство. Привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
