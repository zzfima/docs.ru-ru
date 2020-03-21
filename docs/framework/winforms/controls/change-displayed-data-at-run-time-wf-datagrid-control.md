---
title: Изменение отображаемых данных во время выполнения в управлении DataGrid
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142385"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 После создания форм <xref:System.Windows.Forms.DataGrid> Windows с использованием функций времени проектирования можно также <xref:System.Data.DataSet> динамически изменить элементы объекта сетки во время выполнения. Это может включать изменения либо отдельных значений таблицы, либо <xref:System.Windows.Forms.DataGrid> изменение источника данных, привязанного к элементу управления. Изменения в отдельных значениях <xref:System.Data.DataSet> выполняются <xref:System.Windows.Forms.DataGrid> через объект, а не через элемент управления.  
  
### <a name="to-change-data-programmatically"></a>Программно еменять данные  
  
1. Укажите нужную <xref:System.Data.DataSet> таблицу от объекта и желаемую строку и поле из таблицы и установите ячейку, равную новому значению.  
  
    > [!NOTE]
    > Чтобы указать первую <xref:System.Data.DataSet> таблицу или первый ряд таблицы, используйте 0.  
  
     Ниже приводится следующий пример, как изменить вторую запись первой строки `Button1`первой таблицы набора данных, нажав кнопку . Ранее <xref:System.Data.DataSet> `ds`были созданы`0` `1`() и таблицы (и )  
  
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
  
     (Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Во время выполнения можно <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> использовать метод <xref:System.Windows.Forms.DataGrid> для привязки элемента управления к другому источнику данных. Например, у вас может быть несколько ADO.NET управления данными, каждый из которых подключен к другой базе данных.  
  
### <a name="to-change-the-datasource-programmatically"></a>Изменить DataSource программно  
  
1. Установите <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод к названию источника данных и таблице, к которой вы хотите привязать.  
  
     В следующем примере показано, как <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> изменить источник даты с помощью метода на ADO.NET управления данными (adoPubsAuthors), который подключен к таблице Авторов в базе данных Pubs.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [DataSets в ADO.NET](../../data/adonet/ado-net-datasets.md)
- [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
