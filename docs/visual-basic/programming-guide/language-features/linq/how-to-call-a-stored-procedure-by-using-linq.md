---
title: Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 50a4dff90dc1ce02869978f1da147e530cefc3e1
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874671"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Практическое руководство. Вызов хранимой процедуры с помощью LINQ (Visual Basic)
Language-Integrated Query (LINQ) позволяет легко получить доступ к информации базы данных, включая объекты, такие как хранимые процедуры базы данных.  
  
 В следующем примере показано, как создать приложение, которое вызывает хранимую процедуру в базе данных SQL Server. Образец показан порядок вызова двух различных хранимых процедур в базе данных. Каждая процедура возвращает результаты запроса. Одна процедура принимает входные параметры, а другая процедура не принимает параметров.  
  
 В примерах в этом разделе используется образец базы данных "Борей". Если у вас нет этой базы данных на компьютере разработчика, его можно загрузить из центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Чтобы создать подключение к базе данных  
  
1.  В Visual Studio откройте **обозревателя серверов**/**обозреватель баз данных** , щелкнув **обозревателя серверов**/**базы данных Обозреватель** на **представление** меню.  
  
2.  Щелкните правой кнопкой мыши **подключения к данным** в **обозревателя серверов**/**обозреватель баз данных** и нажмите кнопку **добавить подключение**.  
  
3.  Укажите допустимое соединение с образцом базы данных "Борей".  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Чтобы добавить в проект, содержащий файл классов LINQ to SQL  
  
1.  В меню **Файл** окна Visual Studio наведите указатель мыши на пункт **Создать** и щелкните **Проект**. Выберите Visual Basic **приложение Windows Forms** в качестве типа проекта.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**. Выберите **LINQ to SQL Classes** шаблона элемента.  
  
3.  Назовите файл `northwind.dbml`. Нажмите кнопку **Добавить**. Для файла northwind.dbml открывается реляционный конструктор объектов (O/R Designer).  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Добавление хранимых процедур в конструктор O/R  
  
1.  В **обозревателя серверов**/**обозреватель баз данных**, разверните подключение к базе данных "Борей". Разверните **хранимые процедуры** папки.  
  
     Если вы уже закрыли конструктор O/R, его можно открыть, дважды щелкнув файл northwind.dbml, который был добавлен ранее.  
  
2.  Нажмите кнопку **продаж по годам** хранимую процедуру и перетащите его на правую панель конструктора. Нажмите кнопку **десять самых дорогих продуктов** хранимой процедуры перетащите его на правую панель конструктора.  
  
3.  Сохраните изменения и закройте конструктор.  
  
4.  Сохраните проект.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Чтобы добавить код для отображения результатов хранимых процедур.  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.DataGridView> элемента управления на форме Windows по умолчанию для проекта, Form1.  
  
2.  Дважды щелкните файл Form1, чтобы добавить код для его `Load` событий.  
  
3.  При добавлении хранимых процедур в конструктор O/R, разработчик добавил <xref:System.Data.Linq.DataContext> объект для проекта. Этот объект содержит код, которые необходимы для доступа к этим процедурам. <xref:System.Data.Linq.DataContext> Объектов для проекта присваивается на основе имени из DBML-файл. Для этого проекта <xref:System.Data.Linq.DataContext> объект называется `northwindDataContext`.  
  
     Можно создать экземпляр <xref:System.Data.Linq.DataContext> в коде и вызывать методы хранимой процедуры, указанную конструктором O/R. Для привязки к <xref:System.Windows.Forms.DataGridView> объекта, может потребоваться принудительно выполнять запрос выполняться немедленно, вызвав <xref:System.Linq.Enumerable.ToList%2A> метод результатов хранимой процедуры.  
  
     Добавьте следующий код, чтобы `Load` событий для вызова одной из хранимых процедур, предоставленных как методы в контексте данных.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Нажмите клавишу F5, чтобы запустить проект и просмотреть результаты.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/index.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [Практическое руководство. Назначение хранимых процедур для выполнения обновления, вставки и удаления (реляционный конструктор объектов)](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
