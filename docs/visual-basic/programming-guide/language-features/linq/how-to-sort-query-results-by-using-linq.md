---
title: Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: d2114e908077ec947164a28f48841282abefda2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301221"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a>Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)
Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных и выполнения запросов.  
  
 Приведенный ниже показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и сортирует результаты по нескольким полям с помощью `Order By` предложение. Порядок сортировки для каждого поля можно по возрастанию или убыванию. Дополнительные сведения см. в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 В примерах в этом разделе используется образец базы данных "Борей". Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Чтобы создать подключение к базе данных  
  
1. В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.  
  
2. Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.  
  
3. Укажите допустимое соединение с образцом базы данных "Борей".  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Чтобы добавить в проект, содержащий файл классов LINQ to SQL  
  
1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2. В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **LINQ to SQL Classes** шаблона элемента.  
  
3. Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла northwind.dbml открывается реляционный конструктор объектов (O/R Designer).  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблицы к запросу в конструкторе O/R  
  
1. В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей". Разверните **таблиц** папки.  
  
     Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2. Щелкните таблицу Customers и перетащите его в левую область конструктора. Щелкните в таблице Orders и перетащите его в левую область конструктора.  
  
     Конструктор создает новый `Customer` и `Order` объектов для проекта. Обратите внимание на то, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с клиентом.  
  
3. Сохраните изменения и закройте конструктор.  
  
4. Сохраните проект.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и отображения результатов  
  
1. Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.  
  
2. Дважды щелкните файл Form1, чтобы добавить код для `Load` событий формы.  
  
3. При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект в проект. Этот объект содержит код, который необходимо иметь для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы. <xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запрос таблицы, указанные в конструкторе O/R.  
  
     Добавьте следующий код, чтобы `Load` событий для запроса к таблицам, которые представляются как свойства контекста данных и сортировки результатов. Запрос сортирует результаты по количеству заказов клиентов в порядке убывания. Клиенты, имеющие одинаковое количество заказов упорядочиваются по названию компании по возрастанию (по умолчанию).  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
