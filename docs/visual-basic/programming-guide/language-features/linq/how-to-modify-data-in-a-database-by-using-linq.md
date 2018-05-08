---
title: Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)
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
ms.openlocfilehash: c0c00c15756ab4d488096d4311bb47986a5eb25e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)
Запросы LINQ запросы (LINQ) упрощают доступ к данным базы данных, а также изменять значения в базе данных.  
  
 В следующем примере показано создание нового приложения, которое получает и обновляет сведения в базе данных SQL Server.  
  
 Примеры в этом разделе используется образец базы данных "Борей". Если у вас образца базы данных "Борей" на компьютере разработчика, его можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
### <a name="to-create-a-connection-to-a-database"></a>Чтобы создать подключение к базе данных  
  
1.  В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **представление** меню, а затем выберите **обозревателя серверов** / **Проводника баз данных**.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных**и нажмите кнопку **добавить подключение**.  
  
3.  Укажите допустимое подключение к учебной базе данных "Борей".  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Чтобы добавить проект с LINQ to SQL-файл  
  
1.  В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **LINQ to SQL Classes** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Реляционный конструктор объектов (O/R-конструктор) открыт для `northwind.dbml` файла.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Добавление таблицы к запросу и изменить в конструкторе  
  
1.  В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind. Разверните **таблиц** папки.  
  
     Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув `northwind.dbml` файл, который был добавлен ранее.  
  
2.  Щелкните таблицу Customers и перетащите его в левую область конструктора.  
  
     Конструктор создает новый объект Customer для проекта.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Чтобы добавить код для изменения базы данных и отображения результатов  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.  
  
2.  При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объекта к проекту. Этот объект содержит код, который можно использовать для доступа к таблице Customers. Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы. <xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> объекта в коде и запросов и изменение коллекции клиентов, указанной в реляционный конструктор объектов. Изменения, внесенные в коллекцию Customers, не отражаются в базе данных до их отправки, вызвав <xref:System.Data.Linq.DataContext.SubmitChanges%2A> метод <xref:System.Data.Linq.DataContext> объекта.  
  
     Дважды щелкните Windows форму Form1, чтобы добавить код для <xref:System.Windows.Forms.Form.Load> событий для запросов в таблице Customers, который предоставляется как свойство вашей <xref:System.Data.Linq.DataContext>. Добавьте следующий код:  
  
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
  
3.  Из **элементов**, перетащите три <xref:System.Windows.Forms.Button> элементов управления в форму. Выберите первую `Button` элемента управления. В **свойства** задайте `Name` из `Button` управления `AddButton` и `Text` для `Add`. Выберите вторую кнопку и задайте `Name` свойства `UpdateButton` и `Text` свойства `Update`. Выберите третий кнопку и задайте `Name` свойства `DeleteButton` и `Text` свойства `Delete`.  
  
4.  Дважды щелкните **добавить** кнопку, чтобы добавить код, чтобы его `Click` событий. Добавьте следующий код:  
  
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
  
5.  Дважды щелкните **обновление** кнопку, чтобы добавить код, чтобы его `Click` событий. Добавьте следующий код:  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  Дважды щелкните **удаление** кнопку, чтобы добавить код, чтобы его `Click` событий. Добавьте следующий код:  
  
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
  
7.  Нажмите клавишу F5 для запуска проекта. Нажмите кнопку **добавить** для добавления новой записи. Нажмите кнопку **обновление** для изменения новой записи. Нажмите кнопку **удаление** для удаления новой записи.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Методы DataContext (O/R-конструктор)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
