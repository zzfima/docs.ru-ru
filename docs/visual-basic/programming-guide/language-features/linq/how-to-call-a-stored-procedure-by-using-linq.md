---
title: Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 8aad85ce3369f84e82100072bccf389b03c38221
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "34826923"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
Встроенные в язык запросы (LINQ) позволяет легко получить доступ к данным базы данных, включая объекты, такие как сохраненные процедуры базы данных.  
  
 В следующем примере показано, как создать приложение, которое вызывает хранимую процедуру в базе данных SQL Server. Образец показан порядок вызова две различные хранимые процедуры в базе данных. Каждая процедура возвращает результаты запроса. Одна процедура принимает входные параметры, а другая процедура не принимает параметров.  
  
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
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Для добавления в конструктор O/R хранимые процедуры  
  
1.  В **обозревателя серверов**/**обозревателя базы данных**, разверните подключение к базе данных Northwind. Разверните **хранимых процедур** папки.  
  
     Если O/R-конструктор закрыт, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Нажмите кнопку **Sales by Year** хранимую процедуру и перетащите его в правую область конструктора. Нажмите кнопку **десять самых дорогостоящих товаров** хранимой процедуры перетащите ее правую область конструктора.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Чтобы добавить код для отображения результатов хранимых процедур.  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> на форме Windows Forms по умолчанию для проекта, Form1 элемент управления.  
  
2.  Дважды щелкните файл Form1, чтобы добавить код для его `Load` событий.  
  
3.  При добавлении хранимых процедур в конструктор O/R конструктор добавил <xref:System.Data.Linq.DataContext> объектов для проекта. Этот объект содержит код, который должен иметь для доступа к этим процедурам. <xref:System.Data.Linq.DataContext> Объектов для проекта присваивается на основе имени из DBML-файла. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и вызывать методы хранимой процедуры указано O/R-конструктором. Для привязки к <xref:System.Windows.Forms.DataGridView> объекта, необходимо принудительно выполнить запрос немедленно путем вызова <xref:System.Linq.Enumerable.ToList%2A> метод в результатах хранимой процедуры.  
  
     Добавьте следующий код в `Load` событий для вызова одной из хранимых процедур, предоставленных как методы в контексте данных.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Нажмите клавишу F5 для запуска проекта и просмотреть результаты.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Методы DataContext (O/R-конструктор)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
