---
title: Как выполнить  Изменение данных в базе данных с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: 88597e5cfa1db46e147b829c8ffc634697cecc7e
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739492"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Как выполнить  Изменение данных в базе данных с помощью LINQ (Visual Basic)
Запросы Language-Integrated Query (LINQ) упрощают доступ к данным базы данных и измените значения в базе данных.  
  
 В примере показан способ создания нового приложения, которое извлекает и обновляет сведения в базе данных SQL Server.  
  
 В примерах в этом разделе используется образец базы данных "Борей". Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
### <a name="to-create-a-connection-to-a-database"></a>Чтобы создать подключение к базе данных  
  
1.  В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **представление** меню, а затем выберите **обозревателя серверов** / **Проводника баз данных**.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных**и нажмите кнопку **добавить подключение**.  
  
3.  Укажите допустимое соединение с образцом базы данных "Борей".  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Добавление проекта с помощью LINQ to SQL-файл  
  
1.  В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **LINQ to SQL Classes** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Открывается реляционный конструктор объектов (O/R Designer) для `northwind.dbml` файла.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Чтобы добавить таблицы в запрос и изменение в конструктор  
  
1.  В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей". Разверните **таблиц** папки.  
  
     Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув `northwind.dbml` файл, который был добавлен ранее.  
  
2.  Щелкните таблицу Customers и перетащите его в левую область конструктора.  
  
     Конструктор создает новый объект Customer для проекта.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Добавление кода для изменения базы данных и отображения результатов  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.  
  
2.  При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект в проект. Этот объект содержит код, который можно использовать для доступа к таблице Customers. Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы. <xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> объекта в коде и запрос и изменение коллекции клиентов, указанной в реляционный конструктор объектов. Изменения, внесенные в коллекцию клиентов не отражаются в базе данных до их отправки, вызвав <xref:System.Data.Linq.DataContext.SubmitChanges%2A> метод <xref:System.Data.Linq.DataContext> объекта.  
  
     Дважды щелкните форму Windows, Form1, чтобы добавить код для <xref:System.Windows.Forms.Form.Load> событий для запроса, в таблице Customers, который предоставляется как свойство вашей <xref:System.Data.Linq.DataContext>. Добавьте следующий код:  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  Из **элементов**, перетащите три <xref:System.Windows.Forms.Button> элементов управления в форму. Выберите первую `Button` элемента управления. В **свойства** окне `Name` из `Button` управления `AddButton` и `Text` для `Add`. Выберите второй кнопки и задайте `Name` свойства `UpdateButton` и `Text` свойства `Update`. Выберите третью кнопку и задайте `Name` свойства `DeleteButton` и `Text` свойства `Delete`.  
  
4.  Дважды щелкните **добавить** , чтобы добавить код для его `Click` событий. Добавьте следующий код:  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  Дважды щелкните **обновление** , чтобы добавить код для его `Click` событий. Добавьте следующий код:  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  Дважды щелкните **удалить** , чтобы добавить код для его `Click` событий. Добавьте следующий код:  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  Нажмите клавишу F5 для запуска проекта. Нажмите кнопку **добавить** для добавления новой записи. Нажмите кнопку **обновления** изменение новой записи. Нажмите кнопку **удалить** для удаления новой записи.  
  
## <a name="see-also"></a>См. также
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
