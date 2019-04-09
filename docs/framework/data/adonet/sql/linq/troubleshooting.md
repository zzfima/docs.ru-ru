---
title: Устранение неполадок
ms.date: 03/30/2017
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
ms.openlocfilehash: 27b7eef345dd8ec6c4f5e319818b6b002717f049
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105486"
---
# <a name="troubleshooting"></a>Устранение неполадок
В данном материале представлен ряд проблем, которые могут возникнуть в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], и даны рекомендации, как их избежать или, по крайней мере, снизить их негативное влияние.  
  
 Дополнительные проблемы рассматриваются в [вопросы и ответы](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md).  
  
## <a name="unsupported-standard-query-operators"></a>Неподдерживаемые стандартные операторы запросов  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает не все методы стандартных операторов запросов (например, <xref:System.Linq.Enumerable.ElementAt%2A>). В результате компилируемых проектов могут по-прежнему возникать ошибки во время выполнения. Дополнительные сведения см. в разделе [преобразование стандартного оператора запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
## <a name="memory-issues"></a>Проблемы с использованием памяти  
 Если запрос включает в себя коллекцию в памяти и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>, запрос может быть выполнен в памяти, в зависимости от порядка, в котором указаны две коллекции. Если запрос следует выполнить в памяти, извлекать данные из таблицы базы данных нет необходимости.  
  
 Этот способ неэффективен и может привести к потреблению значительных ресурсов памяти и процессора. Попытайтесь исключить подобные мультидоменные запросы.  
  
## <a name="file-names-and-sqlmetal"></a>Имена файлов и средство SQLMetal  
 Чтобы указать имя входного файла, добавьте имя в командную строку в качестве входного файла. Включение имени файла в строку подключения (параметром **/conn** ) не поддерживается. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="class-library-projects"></a>Проекты библиотеки классов  
 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] создает строку подключения в файле `app.config` проекта. Файл `app.config` не используется в проектах библиотек классов. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует строку подключения, предоставленную в файлах во время разработки. Изменение значения в `app.config` не приводит к изменениям базы данных, к которой подключается приложение.  
  
## <a name="cascade-delete"></a>Каскадное удаление  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любое из следующих действий.  
  
-   Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.  
  
-   Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.  
  
 В противном случае возникнет исключение <xref:System.Data.SqlClient.SqlException>.  
  
 Дополнительные сведения см. в разделе [Как Удаление строк из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
## <a name="expression-not-queryable"></a>Выражение, не подходящее для запроса  
 Если вы получаете «выражение [выражение] не поддерживает запросы; Возможно, отсутствует ссылка на сборку?» Ошибка, убедитесь, что из следующих:  
  
-   Приложение предназначено для выполнения в [!INCLUDE[compact_v35_short](../../../../../../includes/compact-v35-short-md.md)].  
  
-   Наличие ссылки на `System.Core.dll` и `System.Data.Linq.dll`.  
  
-   У вас есть `Imports` (Visual Basic) или `using` директива (C#) для <xref:System.Linq> и <xref:System.Data.Linq>.  
  
## <a name="duplicatekeyexception"></a>DuplicateKeyException  
 Во время отладки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта, можно переходить через отношения сущности. Таким образом должен связать эти элементы в кэш, и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] узнает о своем присутствии. Если после этого предпринимается попытка выполнения метода <xref:System.Data.Linq.Table%601.Attach%2A>, или <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, или аналогичного, результатом которого являются несколько строк с одинаковым ключом, создается исключение <xref:System.Data.Linq.DuplicateKeyException>.  
  
## <a name="string-concatenation-exceptions"></a>Исключения при объединении строк  
 Объединение в операндах, сопоставленных с `[n]text` и другими `[n][var]char`, не поддерживается. При объединении строк, сопоставленных двум разным наборам типов, возникает исключение. Дополнительные сведения см. в разделе [методы System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md).  
  
## <a name="skip-and-take-exceptions-in-sql-server-2000"></a>Исключения методов "Skip" и "Take" в SQL Server 2000  
 При использовании <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> или <xref:System.Linq.Queryable.Take%2A> в базе данных SQL Server 2000 необходимо применять члены идентификации (<xref:System.Linq.Queryable.Skip%2A>) Запрос должен быть выполнен в одной таблице (без объединения) либо он должен представлять операцию <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> или <xref:System.Linq.Queryable.Union%2A> и не включать операцию <xref:System.Linq.Queryable.Concat%2A> operation. Дополнительные сведения см. в разделе «Поддержка SQL Server 2000» [преобразование стандартного оператора запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
 Это требование не относится к [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
## <a name="groupby-invalidoperationexception"></a>GroupBy InvalidOperationException  
 Данное исключение возникает, если в запросе <xref:System.Linq.Enumerable.GroupBy%2A>, выполняющем группировку по выражению `boolean`, например `group x by (Phone==@phone)`, столбец имеет значение NULL. Поскольку выражение является `boolean`, ключ определяется как `boolean`, а не `nullable` `boolean`. При результате преобразованного сравнения выводится значение null, будет предпринята попытка назначить `nullable` `boolean` для `boolean`, и возникает исключение.  
  
 Чтобы избежать такой ситуации (предполагается, что значения NULL оцениваются как ложные), воспользуйтесь следующим способом.  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## <a name="oncreated-partial-method"></a>Разделяемый метод OnCreated()  
 Созданный метод `OnCreated()` вызывается при каждом вызове конструктора объектов, включая моменты, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывает его для копирования исходных значений. При реализации метода `OnCreated()` в собственном разделяемом классе данное поведение следует принять во внимание.  
  
## <a name="see-also"></a>См. также

- [Поддержка отладки](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
- [Вопросы и ответы](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
