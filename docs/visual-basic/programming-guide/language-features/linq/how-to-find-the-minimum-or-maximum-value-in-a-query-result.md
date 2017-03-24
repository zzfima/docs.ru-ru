---
title: "Практическое руководство: поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
caps.latest.revision: 6
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
ms.openlocfilehash: 6dc2eecf4cef9a219b7a06cfcc0fdf773e4e1333
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Практическое руководство. Поиск минимального или максимального значения в результатах запроса с помощью LINQ (Visual Basic)
Language Integrated Query (LINQ) упрощает для доступа к базе данных и выполнения запросов.  
  
 Следующий пример демонстрирует создание нового приложения, выполняющего запросы к базе данных SQL Server. В примере определяются минимальное и максимальное значения для результатов с помощью `Aggregate` и `Group By` предложения. Дополнительные сведения см. в разделе [предложения Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 Примеры в этом разделе используется образец базы данных Northwind. Если у вас образца базы данных "Борей" на компьютере разработчика, можно загрузить из [центра загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkID=98088) веб-сайта. Инструкции см. в разделе [Загрузка примеров баз данных](https://msdn.microsoft.com/library/bb399411).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
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
  
3.  При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext> Этот объект содержит код, который должен иметь доступ к этим таблицам, в дополнение к отдельным объектам и коллекциям для каждой таблицы. <xref:System.Data.Linq.DataContext>Объект для проекта имя на основе имени файла .dbml.</xref:System.Data.Linq.DataContext> Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и запросить таблицы, указанные в реляционный конструктор объектов.</xref:System.Data.Linq.DataContext>  
  
     Добавьте следующий код в `Load` событий. Этот код запрашивает таблицы, которые представляются как свойства в контексте данных и определяет минимальное и максимальное значения для результатов. Пример использует `Aggregate` предложение для запроса одного результата и `Group By` предложения для отображения среднего значения для сгруппированных результатов.  
  
     [!code-vb[VbLINQToSQLHowTos&#14;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]  
  
4.  Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)

