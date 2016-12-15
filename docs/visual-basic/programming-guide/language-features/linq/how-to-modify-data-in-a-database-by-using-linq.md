---
title: "Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "данные [Visual Basic], обновление"
  - "удаление данных"
  - "удаление строк [LINQ to SQL]"
  - "вставка данных [Visual Basic]"
  - "вставка строк [LINQ to SQL]"
  - "запросы [LINQ в Visual Basic], изменение данных в базе данных"
  - "запросы [LINQ в Visual Basic], разделы практического руководства"
  - "обновление данных [LINQ]"
  - "обновление строк [LINQ to SQL]"
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Изменение данных в базе данных с помощью LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Запросы языка интегрированных запросов \(LINQ\) упрощают доступ к сведениям базы данных и изменение значений в базе данных.  
  
 В следующем примере показано создание нового приложения, которое получает и обновляет сведения в базе данных SQL Server.  
  
 В примерах этого раздела используется учебная база данных "Борей".  При отсутствии учебной базы данных "Борей" на компьютере разработчика ее можно загрузить с веб\-узла [Центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088).  Подробные инструкции см. в разделе [Загрузка образцов баз данных](../Topic/Downloading%20Sample%20Databases.md).  
  
### Создание подключения к базе данных  
  
1.  В Visual Studio откройте **Обозреватель серверов**\/**Обозреватель базы данных**, щелкнув **Обозреватель серверов**\/**Обозреватель базы данных** в меню **Вид**.  
  
2.  Щелкните правой кнопкой мыши **Подключения данных** в **Обозреватель серверов**\/**Обозреватель базы данных** и затем щелкните **Добавить подключение**.  
  
3.  Укажите допустимое подключение к учебной базе данных "Northwind".  
  
### Чтобы добавить проект, с LINQ для SQL  
  
1.  В меню **Файл** окна Visual Studio выберите команду **Создать** и щелкните **Проект**.  Выберите **Приложение Windows Forms** в качестве типа проекта Visual Basic.  
  
2.  В меню **Проект** выберите команду **Добавить новый элемент**.  Выберите шаблон элемента **Классы LINQ\-SQL**.  
  
3.  Назовите файл `northwind.dbml`.  Нажмите кнопку **Добавить**.  Реляционный конструктор объектов \(O\/R\-конструктор\) открыт для файла `northwind.dbml`.  
  
### Чтобы добавить таблицы к запросу и изменить в конструкторе  
  
1.  В представлении **Обозреватель серверов** или **Обозреватель баз данных** разверните подключение к базе данных "Northwind".  Разверните папку **Таблицы**.  
  
     Если O\/R\-конструктор закрыт, его можно открыть, дважды щелкнув файл `northwind.dbml`, добавленный ранее.  
  
2.  Щелкните таблицу "Клиенты" и перетащите ее в левую область конструктора.  
  
     Конструктор создает новый объект Customer для проекта.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### Чтобы добавить код изменения базы данных и отображения результатов  
  
1.  С **панели элементов** перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в заданную по умолчанию форму Windows Forms для проекта \(Form1\).  
  
2.  При добавлении таблиц в реляционный конструктор объектов конструктор добавил объект <xref:System.Data.Linq.DataContext> в проект.  Этот объект содержит код, который можно использовать для доступа к таблице Customers.  Он также содержит код, который определяет локальный объект Customer и коллекцию Customers для таблицы.  Объекту <xref:System.Data.Linq.DataContext> для проекта присвоено имя на основе имени файла .dbml.  Для данного проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.  
  
     Можно создать экземпляр объекта <xref:System.Data.Linq.DataContext> в коде и запросе и изменить коллекцию Customers, определенную в конструкторе O\/R.  Изменения, внесенные в коллекцию Customers, не отражаются в базе данных до тех пор, пока их отправить туда вызовом метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> объекта <xref:System.Data.Linq.DataContext>.  
  
     Дважды щелкните форму Windows Form1, чтобы добавить код в событие <xref:System.Windows.Forms.Form.Load> для запроса к таблице Customers, который предоставляется как свойство элемента<xref:System.Data.Linq.DataContext>.  Добавьте следующий код:  
  
    ```vb#  
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
  
3.  Из **панели элементов** перетащите на форму 3 элемента управления <xref:System.Windows.Forms.Button>.  Выберите первый элемент управления `Button`.  В окне **Свойства** задайте свойству `Name` элемента управления `Button` значение `AddButton` и свойству `Text` значение `Add`.  Выберите вторую кнопку и задайте свойству `Name` значение `UpdateButton` и свойству `Text` значение `Update`.  Выберите третью кнопку и задайте свойству `Name` значение `DeleteButton` и свойству `Text` значение `Delete`.  
  
4.  Дважды щелкните кнопку **Add** для добавления кода к событию `Click` этой кнопки.  Добавьте следующий код:  
  
    ```vb#  
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
  
5.  Дважды щелкните кнопку **Update** для добавления кода к событию `Click` этой кнопки.  Добавьте следующий код:  
  
    ```vb#  
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
  
6.  Дважды щелкните кнопку **Delete** для добавления кода к событию `Click` этой кнопки.  Добавьте следующий код:  
  
    ```vb#  
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
  
7.  Нажмите клавишу F5 для запуска проекта.  Нажмите кнопку **Add** для добавления новой записи.  Нажмите кнопку **Update** для изменения новой записи.  Нажмите кнопку **Delete** для удаления новой записи.  
  
## См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Методы DataContext \(реляционный конструктор объектов\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Как назначить хранимые процедуры для выполнения обновлений, вставок и удалений \(реляционный конструктор объектов\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Пошаговое руководство. Создание классов LINQ to SQL \(реляционный конструктор объектов\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)