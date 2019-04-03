---
title: Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)
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
ms.openlocfilehash: 4de6ed4436f6a1769d178508210ed20e0162f647
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822886"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Практическое руководство. Фильтрование результатов запроса с помощью LINQ (Visual Basic)
Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных и выполнения запросов.  
  
 Приведенный ниже показано, как создать новое приложение, которое выполняет запросы к базе данных SQL Server и фильтрует результаты по определенному значению, используя `Where` предложение. Дополнительные сведения см. в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
 В примерах в этом разделе используется образец базы данных "Борей". Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Чтобы создать подключение к базе данных  
  
1.  В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.  
  
3.  Укажите допустимое соединение с образцом базы данных "Борей".  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Чтобы добавить в проект, содержащий файл классов LINQ to SQL  
  
1.  В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **LINQ to SQL Classes** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла northwind.dbml откроется реляционный конструктор объектов (O/R Designer).  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблицы к запросу в конструкторе O/R  
  
1.  В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей". Разверните **таблиц** папки.  
  
     Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Щелкните таблицу Customers и перетащите его в левую область конструктора. Щелкните в таблице Orders и перетащите его в левую область конструктора.  
  
     Конструктор создает новый `Customer` и `Order` объектов для проекта. Обратите внимание на то, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойство для всех заказов, связанных с клиентом.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и отображения результатов  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.  
  
2.  Дважды щелкните файл Form1, чтобы добавить код для `Load` событий формы.  
  
3.  При добавлении таблиц в конструктор O/R designer добавлены <xref:System.Data.Linq.DataContext> объект для проекта. Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы. <xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запрос таблицы, указанные в конструкторе O/R.  
  
     Добавьте следующий код, чтобы `Load` событий для запроса к таблицам, которые представляются как свойства контекста данных. Запрос фильтрует результаты и возвращает только те клиенты, которые находятся в папке `London`.  
  
     [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]  
  
4.  Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
5.  Ниже приведены другие фильтры, которые вы можете попробовать.  
  
     [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]  
  
## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
