---
title: "Практическое руководство: изменение данных в базе данных с помощью LINQ (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 44ca3e44d8411a6329d176eb778677bfab2b365c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)
Запросы Language Integrated Query (LINQ) упрощают для доступа к базе данных, а также изменять значения в базе данных.  
  
 В следующем примере показано создание нового приложения, которое получает и обновляет сведения в базе данных SQL Server.  
  
 Примеры в этом разделе используется образец базы данных Northwind. Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта. Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).  
  
### <a name="to-create-a-connection-to-a-database"></a>Создание подключения к базе данных  
  
1.  В Visual Studio откройте **обозревателя**/**обозреватель баз данных** , щелкнув **представление** меню, а затем выберите **обозреватель серверов**/**обозревателя базы данных**.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных**и нажмите кнопку **Добавление подключения**.  
  
3.  Укажите допустимое подключение к учебной базе данных "Борей".  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>Добавление проекта с LINQ to SQL-файл  
  
1.  В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **классы LINQ to SQL** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Открывается реляционный конструктор объектов (конструктор O/R) для `northwind.dbml` файла.  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>Добавление таблицы к запросу и изменить в конструкторе  
  
1.  В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind. Разверните **таблиц** папки.  
  
     Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув `northwind.dbml` файл, который был добавлен ранее.  
  
2.  Щелкните таблицу Customers и перетащите его в левую область конструктора.  
  
     Конструктор создает новый объект Customer для проекта.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>Добавление кода для изменения базы данных и отображения результатов  
  
1.  От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект в проект.</xref:System.Data.Linq.DataContext> Этот объект содержит код, который можно использовать для доступа к таблице Customers. Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы. <xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext> Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext>объекта в коде и запросе и изменить коллекцию Customers, определенную в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext> Изменения, внесенные в коллекцию Customers, не отражаются в базе данных до их отправки путем вызова <xref:System.Data.Linq.DataContext.SubmitChanges%2A>метод <xref:System.Data.Linq.DataContext>объекта.</xref:System.Data.Linq.DataContext> </xref:System.Data.Linq.DataContext.SubmitChanges%2A>  
  
     Дважды щелкните Windows форму Form1, чтобы добавить код в <xref:System.Windows.Forms.Form.Load>событие для запроса таблицы Customers, который предоставляется как свойство <xref:System.Data.Linq.DataContext>.</xref:System.Data.Linq.DataContext> </xref:System.Windows.Forms.Form.Load> Добавьте следующий код:  
  
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
  
3.  От **элементов**, перетащите три <xref:System.Windows.Forms.Button>элементов управления в форму.</xref:System.Windows.Forms.Button> Выберите первый `Button` элемента управления. В **свойства** установите `Name` из `Button` управления `AddButton` и `Text` в `Add`. Выберите вторую кнопку и задайте `Name` свойства `UpdateButton` и `Text` свойства `Update`. Выберите третью кнопку и задайте `Name` свойства `DeleteButton` и `Text` свойства `Delete`.  
  
4.  Дважды щелкните **добавить** кнопку, чтобы добавить код для его `Click` события. Добавьте следующий код:  
  
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
  
5.  Дважды щелкните **обновление** кнопку, чтобы добавить код для его `Click` события. Добавьте следующий код:  
  
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
  
6.  Дважды щелкните **удаление** кнопку, чтобы добавить код для его `Click` события. Добавьте следующий код:  
  
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
  
7.  Нажмите клавишу F5 для запуска проекта. Щелкните **добавить** для добавления новой записи. Щелкните **обновление** для изменения новой записи. Щелкните **удаление** для удаления новой записи.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [Практическое руководство: назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
