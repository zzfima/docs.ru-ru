---
title: "Практическое руководство. Выполнение над данными функций Count, Sum и Average с помощью LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "Aggregate - предложение"
  - "aggregate - оператор [LINQ в Visual Basic]"
  - "статистические запросы"
  - "average - оператор [LINQ в Visual Basic]"
  - "count - оператор [LINQ в Visual Basic]"
  - "запросы [LINQ в Visual Basic], статистические запросы"
  - "запросы [LINQ в Visual Basic], подсчет результатов"
  - "запросы [LINQ в Visual Basic], разделы практического руководства"
  - "запросы [LINQ в Visual Basic], результаты сложения"
  - "примеры запросов [Visual Basic]"
  - "запрос баз данных [LINQ]"
  - "sum - оператор [LINQ в Visual Basic]"
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Выполнение над данными функций Count, Sum и Average с помощью LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Запросы, интегрированные в язык программирования \(Language\-Integrated Query, LINQ\), упрощают доступ к содержимому базы данных и обеспечивают выполнение запросов.  
  
 В следующем примере демонстрируется создание нового приложения, выполняющего запросы к базе данных SQL Server.  Пример подсчитывает, суммирует и усредняет результаты с помощью предложений `Aggregate` и `Group By`.  Дополнительные сведения см. в разделах [Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 В примерах этого раздела используется учебная база данных "Борей".  При отсутствии учебной базы данных "Борей" на компьютере разработчика ее можно загрузить с веб\-узла [Центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088).  Подробные инструкции см. в разделе [Загрузка образцов баз данных](../Topic/Downloading%20Sample%20Databases.md).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Создание подключения к базе данных  
  
1.  В Visual Studio откройте **обозреватель серверов** или **обозреватель баз данных**. Для этого в меню **Вид** выберите пункт **Обозреватель серверов** или **Обозреватель баз данных**.  
  
2.  В **обозревателе серверов** или **обозревателе баз данных** щелкните правой кнопкой мыши **Подключения данных**, а затем выберите команду **Добавить подключение**.  
  
3.  Укажите допустимое подключение к учебной базе данных "Northwind".  
  
### Добавление проекта, содержащего файл LINQ\-SQL  
  
1.  В меню **Файл** окна Visual Studio выберите команду **Создать** и щелкните **Проект**.  Выберите **Приложение Windows Forms** в качестве типа проекта Visual Basic.  
  
2.  В меню **Проект** выберите команду **Добавить новый элемент**.  Выберите шаблон элемента **Классы LINQ\-SQL**.  
  
3.  Назовите файл `northwind.dbml`.  Нажмите кнопку **Добавить**.  Откроется реляционный конструктор объектов для файла northwind.dbml.  
  
### Добавление таблицы к запросу в объектно\-реляционном конструкторе  
  
1.  В представлении **Обозреватель серверов** или **Обозреватель баз данных** разверните подключение к базе данных "Northwind".  Разверните папку **Таблицы**.  
  
     Если реляционный конструктор объектов закрыт, откройте его снова, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Щелкните таблицу "Клиенты" и перетащите ее в левую область конструктора.  Щелкните таблицу "Заказы" и перетащите ее в левую область конструктора.  
  
     Для проекта в конструкторе создаются новые объекты `Customer` и `Order`.  Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов.  Например, функция IntelliSense покажет, что в объекте `Customer` имеется свойство `Orders` для всех заказов, связанных с клиентом.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### Добавление кода в запрос к базе данных и отображение результатов  
  
1.  С **панели элементов** перетащите элемент управления <xref:System.Windows.Forms.DataGridView> в заданную по умолчанию форму Windows Forms для проекта \(Form1\).  
  
2.  Дважды щелкните Form1, чтобы добавить код в событие формы `Load`.  
  
3.  При добавлении таблиц объектно\-реляционный конструктор добавляет в проект объект <xref:System.Data.Linq.DataContext>.  Этот объект содержит код, необходимый для доступа к этим таблицам и доступа к отдельным объектам и коллекциям для каждой таблицы.  Объекту <xref:System.Data.Linq.DataContext> для проекта присвоено имя на основе имени файла .dbml.  Для данного проекта объект <xref:System.Data.Linq.DataContext> называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, указанные реляционным конструктором объектов.  
  
     Добавьте следующий код к событию `Load` для запроса таблиц, которые отображаются как свойства <xref:System.Data.Linq.DataContext>, результаты подсчитываются, суммируются, вычисляется среднее.  Пример использует предложение `Aggregate` для запроса одного результата и предложение `Group By` для отображения среднего значения сгруппированных результатов.  
  
     [!code-vb[VbLINQToSQLHowTos#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]  
  
4.  Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Методы DataContext \(реляционный конструктор объектов\)](/visual-studio/data-tools/datacontext-methods-o-r-designer)   
 [Пошаговое руководство. Создание классов LINQ to SQL \(реляционный конструктор объектов\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [Предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md)