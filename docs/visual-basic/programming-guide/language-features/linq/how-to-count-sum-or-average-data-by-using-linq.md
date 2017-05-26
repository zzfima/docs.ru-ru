---
title: "Практическое руководство: число, суммы или среднего значения данных с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c5789d9e4bee1388d5ad0368f88fad5c1b6e95cc
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a>Практическое руководство. Выполнение над данными функций Count, Sum и Average с помощью LINQ (Visual Basic)
Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.  
  
 Следующий пример демонстрирует создание нового приложения, выполняющего запросы к базе данных SQL Server. Пример подсчитывает, суммирует и усредняет результаты с помощью `Aggregate` и `Group By` предложения. Дополнительные сведения см. в разделе [предложения Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 Примеры в этом разделе используется образец базы данных Northwind. Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта. Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Создание подключения к базе данных  
  
1.  В Visual Studio откройте **обозреватель серверов**/**обозревателя базы данных** , щелкнув **обозревателя**/**обозреватель баз данных** на **представление** меню.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя**/**обозревателя базы данных** и нажмите кнопку **Добавление подключения**.  
  
3.  Укажите допустимое подключение к учебной базе данных "Борей".  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Добавление проекта, содержащего файл LINQ to SQL  
  
1.  В Visual Studio на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **классы LINQ to SQL** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Реляционный конструктор объектов (конструктор O/R) открыт для файла northwind.dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблицы к запросу реляционный конструктор объектов  
  
1.  В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind. Разверните **таблиц** папки.  
  
     Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Щелкните таблицу Customers и перетащите его в левую область конструктора. Щелкните в таблице Orders и перетащите его в левую область конструктора.  
  
     Конструктор создает новый `Customer` и `Order` объекты для проекта. Обратите внимание, что конструктор автоматически обнаруживает связи между таблицами и создает дочерние свойства для связанных объектов. Например, IntelliSense покажет, что `Customer` объект имеет `Orders` свойства для всех заказов, связанных с клиентом.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Чтобы добавить код для запроса к базе данных и отображения результатов  
  
1.  От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Дважды щелкните Form1, чтобы добавить код для `Load` события формы.  
  
3.  При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext> Этот объект содержит код, необходимый для доступа к этим таблицам и доступа к отдельным объектам и коллекциям для каждой таблицы. <xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext> Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext>  
  
     Добавьте следующий код в `Load` событий для запроса к таблицам, которые отображаются как свойства вашего <xref:System.Data.Linq.DataContext>и count, sum и среднее результаты.</xref:System.Data.Linq.DataContext> В образце используется `Aggregate` предложение для запроса одного результата и `Group By` предложения для отображения среднего значения для сгруппированных результатов.  
  
     [!code-vb[VbLINQToSQLHowTos&#13;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]  
  
4.  Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Aggregate-предложение](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md)

