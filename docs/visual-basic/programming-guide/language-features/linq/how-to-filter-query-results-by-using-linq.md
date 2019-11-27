---
title: Инструкции. Фильтрация результатов запроса с помощью LINQ
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
ms.openlocfilehash: 2ea8a852a2f012ddb25ec1198c66e09df880ff47
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344991"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)

LINQ позволяет легко получить доступ к сведениям о базе данных и выполнить запросы.

В следующем примере показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению с помощью предложения `Where`. Дополнительные сведения см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).

В примерах этого раздела используется учебная база данных Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка образцов баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a>Создание соединения с базой данных

1. В Visual Studio откройте **обозреватель сервера**/**обозреватель базы данных** , выбрав **Обозреватель сервера**/**Обозреватель базы данных** в меню **вид** .

2. Щелкните правой кнопкой мыши элемент **подключения к данным** в **Обозреватель сервера**/**Обозреватель базы данных** а затем нажмите кнопку **Добавить подключение**.

3. Укажите допустимое соединение с образцом базы данных Northwind.

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL

1. В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **Windows Forms приложение** в качестве типа проекта.

2. В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите шаблон элемента **LINQ to SQL классы** .

3. Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла Northwind. dbml откроется реляционный конструктор объектов (реляционный конструктор R).

## <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблиц в запрос в реляционный конструктор O/R

1. В **обозреватель сервера**/**Обозреватель базы данных**разверните подключение к базе данных Northwind. Разверните папку **таблицы** .

     Если вы закрыли конструктор O/R, его можно открыть повторно, дважды щелкнув файл Northwind. dbml, который вы добавили ранее.

2. Щелкните таблицу Customers (клиенты) и перетащите ее на левую панель конструктора. Щелкните таблицу Orders и перетащите ее на левую панель конструктора.

     Конструктор создает в проекте новые `Customer` и `Order` объекты. Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что объект `Customer` имеет свойство `Orders` для всех заказов, связанных с этим клиентом.

3. Сохраните изменения и закройте конструктор.

4. Сохраните проект.

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и вывода результатов

1. Из **панели элементов**перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в форму Windows по умолчанию для проекта, Form1.

2. Дважды щелкните Form1, чтобы добавить код в событие `Load` формы.

3. При добавлении таблиц в реляционный конструктор объектов конструктор добавил объект <xref:System.Data.Linq.DataContext> для проекта. Этот объект содержит код, который необходим для доступа к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы. Имя объекта <xref:System.Data.Linq.DataContext> для проекта определяется на основе имени DBML-файла. Для этого проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.

    Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, заданные конструктором O/R.

    Добавьте следующий код в событие `Load`, чтобы запросить таблицы, предоставляемые как свойства контекста данных. Запрос фильтрует результаты и возвращает только клиентов, расположенных в `London`.

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.

5. Ниже приведены некоторые другие фильтры, которые можно использовать.

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
