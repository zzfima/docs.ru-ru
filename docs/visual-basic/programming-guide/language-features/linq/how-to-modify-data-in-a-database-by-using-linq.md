---
title: Инструкции. изменение данных в базе данных с помощью LINQ
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
ms.openlocfilehash: 9a10efef5ae92dd21888594ae80a3fc07869a8c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344948"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)

Запросы LINQ позволяют легко получить доступ к сведениям о базе данных и изменить значения в базе данных.

В следующем примере показано, как создать новое приложение, которое извлекает и обновляет сведения в базе данных SQL Server.

В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

### <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных

1. В Visual Studio откройте **обозреватель сервера**/**Обозреватель базы данных** , выбрав в меню **вид** пункт **Обозреватель сервера**/**Обозреватель базы данных**.

2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных**и выберите команду **Добавить подключение**.

3. Укажите допустимое соединение с образцом базы данных Northwind.

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Добавление проекта с файлом LINQ to SQL

1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.

2. В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .

3. Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла `northwind.dbml` открыт реляционный конструктор объектов (реляционный конструктор R).

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Добавление таблиц к запросам и их изменение в конструкторе

1. В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **таблицы** .

     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл `northwind.dbml`, который был добавлен ранее.

2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора.

     Конструктор создает новый объект Customer для вашего проекта.

3. Сохраните изменения и закройте конструктор.

4. Сохраните проект.

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Добавление кода для изменения базы данных и вывода результатов

1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.

2. При добавлении таблиц в реляционный конструктор объектов конструктор добавил в проект объект <xref:System.Data.Linq.DataContext>. Этот объект содержит код, который можно использовать для доступа к таблице Customers. Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы. Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла. Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.

     Можно создать экземпляр объекта <xref:System.Data.Linq.DataContext> в коде и запросить и изменить коллекцию Customers, указанную в конструкторе O/R. Изменения, вносимые в коллекцию Customers, не отражаются в базе данных, пока они не будут отправлены путем вызова метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> объекта <xref:System.Data.Linq.DataContext>.

     Дважды щелкните форму Windows Forms, форму Form1, чтобы добавить код в событие <xref:System.Windows.Forms.Form.Load>, чтобы запросить таблицу Customers, доступную в качестве свойства <xref:System.Data.Linq.DataContext>. Добавьте следующий код:

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

3. Перетащите на форму три элемента управления <xref:System.Windows.Forms.Button> из **панели элементов**. Выберите первый элемент управления `Button`. В окне **Свойства** задайте для `Name` элемента управления `Button` значение `AddButton` а `Text` — `Add`. Нажмите вторую кнопку и задайте для свойства `Name` значение `UpdateButton` а свойству `Text` — значение `Update`. Нажмите третью кнопку и задайте для свойства `Name` значение `DeleteButton` а свойству `Text` — значение `Delete`.

4. Дважды щелкните кнопку **Добавить** , чтобы добавить код к событию `Click`. Добавьте следующий код:

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

5. Дважды щелкните кнопку " **Обновить** ", чтобы добавить код к событию `Click`. Добавьте следующий код:

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

6. Дважды щелкните кнопку **Удалить** , чтобы добавить код к событию `Click`. Добавьте следующий код:

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

7. Нажмите клавишу F5 для запуска проекта. Нажмите кнопку **Добавить** , чтобы добавить новую запись. Нажмите кнопку **Обновить** , чтобы изменить новую запись. Нажмите кнопку **Удалить** , чтобы удалить новую запись.

## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
