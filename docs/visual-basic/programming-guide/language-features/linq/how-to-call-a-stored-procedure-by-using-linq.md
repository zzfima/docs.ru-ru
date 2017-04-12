---
title: "Практическое руководство: вызов хранимой процедуры с помощью LINQ (Visual Basic) | Документы Microsoft"
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
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: abc3970fc5ab6f4a2f4b67b5efa2b19afb07337b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
Language Integrated Query (LINQ) позволяет легко доступа к базе данных, включая объекты, такие как хранимые процедуры базы данных.  
  
 В следующем примере демонстрируется создание приложения, которое вызывает хранимую процедуру в базе данных SQL Server. Образец показано, как вызвать две различные хранимые процедуры в базе данных. Каждая процедура возвращает результаты запроса. Одна процедура принимает входные параметры, а другая процедура не принимает параметров.  
  
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
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Добавление хранимой процедуры в реляционный конструктор объектов  
  
1.  В **обозревателя**/**обозревателя базы данных**, разверните подключение к базе данных Northwind. Разверните **хранимых процедур** папки.  
  
     Если реляционный конструктор объектов закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Щелкните **Sales by Year** хранимую процедуру и перетащите ее в правую область конструктора. Щелкните **десять самых дорогих продуктов** хранимой процедуры перетащите ее в правую область конструктора.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Чтобы добавить код для отображения результатов хранимых процедур  
  
1.  От **элементов**, перетащите <xref:System.Windows.Forms.DataGridView>элемента управления на форме Windows Forms по умолчанию для проекта, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Дважды щелкните Form1, чтобы добавить код для его `Load` события.  
  
3.  При добавлении хранимых процедур в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext>объект для проекта.</xref:System.Data.Linq.DataContext> Этот объект содержит код, который требуется для доступа к этим процедурам. <xref:System.Data.Linq.DataContext>Объект для присваивается имя на основе имени DBML-файл.</xref:System.Data.Linq.DataContext> Для этого проекта <xref:System.Data.Linq.DataContext>объект называется `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext>в коде и вызывать методы хранимой процедуры, определяемой реляционный конструктор объектов.</xref:System.Data.Linq.DataContext> Для привязки к <xref:System.Windows.Forms.DataGridView>объекта, необходимо принудительно выполнить запрос немедленно путем вызова <xref:System.Linq.Enumerable.ToList%2A>метод результаты хранимой процедуры.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView>  
  
     Добавьте следующий код в `Load` событий для вызова одной из процедур, предоставленных как методы в контексте данных.  
  
     [!code-vb[VbLINQtoSQLHowTos&#1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos&#2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Методы DataContext (реляционный конструктор)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [Практическое руководство: назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)

