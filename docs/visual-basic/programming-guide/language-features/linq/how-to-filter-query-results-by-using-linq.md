---
title: Практическое руководство. Фильтрация результатов запроса с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 1250f2fe0ccd7661b9bc1986000143ec4a15a9f0
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053287"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Практическое руководство. Фильтрация результатов запроса с помощью LINQ (Visual Basic)

LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.

В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению с помощью `Where` предложения. Дополнительные сведения см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).

В примерах этого раздела используется учебная база данных Northwind. Если эта база данных отсутствует на компьютере разработчика, ее можно скачать в центре загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных

1. В Visual Studio откройте **Обозреватель сервера**/**Обозреватель базы данных** , выбрав в меню **вид** пункт **Обозреватель сервера**/**Обозреватель базы данных** .

2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем выберите команду **Добавить подключение**.

3. Укажите допустимое соединение с образцом базы данных Northwind.

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL

1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.

2. В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .

3. Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла Northwind. dbml откроется реляционный конструктор объектов (реляционный конструктор R).

## <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблиц в запрос в реляционный конструктор O/R

1. В **Обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **таблицы** .

     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.

2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора. Щелкните таблицу Orders и перетащите ее на левую панель конструктора.

     Конструктор создает для проекта `Customer` новые `Order` объекты и. Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что `Customer` объект `Orders` имеет свойство для всех заказов, связанных с этим клиентом.

3. Сохраните изменения и закройте конструктор.

4. Сохраните проект.

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и вывода результатов

1. Перетащите<xref:System.Windows.Forms.DataGridView> элемент управления из **области элементов**в форму Windows по умолчанию для проекта, Form1.

2. Дважды щелкните Form1, чтобы добавить код в `Load` событие в форме.

3. При добавлении таблиц в реляционный конструктор <xref:System.Data.Linq.DataContext> объектов конструктор добавил объект для проекта. Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы. Имя <xref:System.Data.Linq.DataContext> объекта для проекта определяется на основе имени DBML-файла. Для этого проекта <xref:System.Data.Linq.DataContext> объект `northwindDataContext`называется.

    <xref:System.Data.Linq.DataContext> В коде можно создать экземпляр класса и запросить таблицы, заданные конструктором O/R.

    Добавьте следующий код в `Load` событие для запроса таблиц, предоставляемых в качестве свойств контекста данных. Запрос фильтрует результаты и возвращает только клиентов, расположенных в `London`.

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.

5. Ниже приведены некоторые другие фильтры, которые можно использовать.

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
