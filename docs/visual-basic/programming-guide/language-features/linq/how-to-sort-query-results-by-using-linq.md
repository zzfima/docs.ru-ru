---
title: Инструкции. Сортировка результатов запроса с помощью LINQ
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
ms.openlocfilehash: 020e4a3800515329b29e2941baf50d3d8add4605
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354169"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a>Практическое руководство. Сортировка результатов запроса с помощью LINQ (Visual Basic)
LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.  
  
 В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и сортирует результаты по нескольким полям с помощью предложения `Order By`. Порядок сортировки для каждого поля может быть упорядочен по возрастанию или по убыванию. Дополнительные сведения см. в разделе [предложение ORDER BY](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных  
  
1. В Visual Studio откройте **обозреватель сервера**/**обозреватель базы данных** , выбрав **Обозреватель сервера**/**Обозреватель базы данных** в меню **вид** .  
  
2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем нажмите кнопку **Добавить подключение**.  
  
3. Укажите допустимое соединение с образцом базы данных Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL  
  
1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.  
  
2. В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .  
  
3. Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла Northwind. dbml открыт реляционный конструктор объектов (реляционный конструктор R).  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблиц в запрос в реляционный конструктор O/R  
  
1. В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **таблицы** .  
  
     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.  
  
2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора. Щелкните таблицу Orders и перетащите ее на левую панель конструктора.  
  
     Конструктор создает в проекте новые `Customer` и `Order` объекты. Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что объект `Customer` имеет свойство `Orders` для всех заказов, связанных с этим клиентом.  
  
3. Сохраните изменения и закройте конструктор.  
  
4. Сохраните проект.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и вывода результатов  
  
1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.  
  
2. Дважды щелкните Form1, чтобы добавить код в событие `Load` формы.  
  
3. При добавлении таблиц в реляционный конструктор объектов конструктор добавил в проект объект <xref:System.Data.Linq.DataContext>. Этот объект содержит код, который необходим для доступа к этим таблицам и для доступа к отдельным объектам и коллекциям для каждой таблицы. Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла. Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, заданные конструктором O/R.  
  
     Добавьте следующий код в событие `Load`, чтобы запросить таблицы, предоставляемые как свойства контекста данных, и отсортировать результаты. Запрос сортирует результаты по количеству заказов клиентов в порядке убывания. Клиенты с одинаковым количеством заказов упорядочиваются по названию компании в возрастающем порядке (по умолчанию).  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
