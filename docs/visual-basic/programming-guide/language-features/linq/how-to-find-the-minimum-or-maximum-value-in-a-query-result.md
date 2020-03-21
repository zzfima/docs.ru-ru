---
title: Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112366"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)
Интегрированный в язык запрос (LINЗ) упрощает доступ к информации базы данных и выполняет запросы.  
  
 В следующем примере показано, как создать новое приложение, выполняя запросы в соответствии с базой данных сервера S'L. Выборка определяет минимальные и максимальные значения результатов `Group By` с помощью ипредложений. `Aggregate` Для получения дополнительной информации [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) [см.](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
  
 Примеры этой темы используют базу данных примеров Northwind. Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Для получения инструкций [см.](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Создание соединения с базой данных  
  
1. В Visual Studio, открыть **Server Explorer**/**Database Explorer,** нажав **Сервер Explorer**/**базы данных Explorer** в меню **просмотра.**  
  
2. Правый клик **подключения к данным** в Server **Explorer**/**Database Explorer,** а затем нажмите **Добавить соединение**.  
  
3. Укажите действительное подключение к базе данных образца Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LIN's в файл S'L  
  
1. В Visual Studio, в меню **файла,** укажите на **новый,** а затем нажмите **Project**. Выберите приложение Visual Basic **Windows Forms** в качестве типа проекта.  
  
2. В меню **Проект** выберите **Добавить новый элемент**. Выберите шаблон элементов **LIN's для классов S'L.**  
  
3. Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Объект реляционный конструктор (O/R Designer) открыт для файла northwind.dbml.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Добавление таблиц в запрос к конструктору O/R  
  
1. В **Server Explorer**/**Database Explorer**расширьте подключение к базе данных Northwind. Разверните папку **Таблицы**.  
  
     Если вы закрыли O/R Designer, вы можете открыть его, дважды нажав на файл northwind.dbml, который вы добавили ранее.  
  
2. Нажмите таблицу Клиентов и перетащите его в левую панель дизайнера. Нажмите на таблицу заказов и перетащите ее в левую панель дизайнера.  
  
     Дизайнер создает `Customer` новые и `Order` объекты для вашего проекта. Обратите внимание, что дизайнер автоматически обнаруживает отношения между таблицами и создает свойства ребенка для связанных объектов. Например, IntelliSense покажет, `Customer` что `Orders` объект имеет свойство для всех заказов, связанных с этим клиентом.  
  
3. Сохраните изменения и закройте дизайнера.  
  
4. Сохраните проект.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса базы данных и отображения результатов  
  
1. Из **toolbox**перетащите <xref:System.Windows.Forms.DataGridView> элемент управления на форму Windows по умолчанию для вашего проекта Form1.  
  
2. Дважды щелкните форму1, чтобы добавить код к событию `Load` формы.  
  
3. При добавлении таблиц в конструктор O/R <xref:System.Data.Linq.DataContext> дизайнер добавляет объект для вашего проекта. Этот объект содержит код, который необходимо получить доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы. Объект <xref:System.Data.Linq.DataContext> для проекта назван на основе имени файла .dbml. Для этого проекта <xref:System.Data.Linq.DataContext> объект `northwindDataContext`называется .  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> кода и заказать таблицы, указанные конструктором O/R.  
  
     Добавьте в событие `Load` следующий код. Этот код запрашивает таблицы, которые разоблачаются как свойства контекста данных, и определяет минимальные и максимальные значения для результатов. В выборке `Aggregate` используется оговорка для запроса `Group By` для одного результата, а в предложении — среднее значение для сгруппированных результатов.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Нажмите **F5,** чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также раздел

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросов](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Методы DataContext (O/R Конструктор)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
