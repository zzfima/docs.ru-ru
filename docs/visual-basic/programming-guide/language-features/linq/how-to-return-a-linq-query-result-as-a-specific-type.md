---
title: Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 2c3a10ed901832846da058018a91349be0c2495b
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827089"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>Практическое руководство. Возвращение результата запроса LINQ в виде определенного типа (Visual Basic)
Встроенные в язык запросы (LINQ) упрощает доступ к данным базы данных и выполнения запросов. По умолчанию запросы LINQ возвращают список объектов как анонимный тип. Можно также указать, чтобы запрос возвращал список определенного типа с помощью `Select` предложения.  
  
 В следующем примере показано создание нового приложения, которое выполняет запросы к базе данных SQL Server и формирует результаты, как конкретный именованный тип. Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) и [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
 Примеры в этом разделе используется образец базы данных "Борей". Если база данных не установлена на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Чтобы создать подключение к базе данных  
  
1.  В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.  
  
3.  Укажите допустимое подключение к учебной базе данных "Борей".  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Чтобы добавить в проект, содержащий файл классов LINQ to SQL  
  
1.  В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **LINQ to SQL Classes** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Реляционный конструктор объектов (O/R-конструктор) открыт для файла northwind.dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Добавление таблицы к запросу в конструкторе O/R  
  
1.  В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind. Разверните **таблиц** папки.  
  
     Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Щелкните таблицу Customers и перетащите его в левую область конструктора.  
  
     Конструктор создает новый `Customer` объектов для проекта. Вы можете проецировать результат запроса как `Customer` тип или тип, который вы создаете. В этом примере будет создать новый тип в процедуре более поздней версии и сформирован результат запроса как тип.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Добавление кода для запроса к базе данных и отображения результатов  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.  
  
2.  Дважды щелкните файл Form1, чтобы изменить класс Form1.  
  
3.  После `End Class` инструкции класса Form1 добавьте следующий код для создания `CustomerInfo` типа для хранения результатов запроса для данного образца.  
  
     [!code-vb[VbLINQToSQLHowTos#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_1.vb)]  
  
4.  При добавлении таблиц в реляционный конструктор объектов конструктор добавил <xref:System.Data.Linq.DataContext> объекта к проекту. Этот объект содержит код, который должен иметь доступа к этим таблицам и получить доступ к отдельным объектам и коллекциям для каждой таблицы. <xref:System.Data.Linq.DataContext> Объектов для проекта имя на основе имени файла .dbml. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и запросить таблицы, указанные в конструкторе O/R.  
  
     В `Load` класса Form1 добавьте следующий код для запроса к таблицам, которые представляются как свойства контекста данных. `Select` Выражение запроса будет создана новая `CustomerInfo` типа вместо анонимного типа для каждого элемента результата запроса.  
  
     [!code-vb[VbLINQToSQLHowTos#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-return-a-linq-query-result-as-a-specific-type_2.vb)]  
  
5.  Нажмите клавишу F5 для запуска проекта и просмотреть результаты.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Методы DataContext (O/R-конструктор)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
