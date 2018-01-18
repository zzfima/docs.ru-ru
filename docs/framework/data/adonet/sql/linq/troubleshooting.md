---
title: "Устранение неполадок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 56d06fa7adf2690a2cb9194342071c7814a4ec4a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="troubleshooting"></a>Устранение неполадок
В данном материале представлен ряд проблем, которые могут возникнуть в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], и даны рекомендации, как их избежать или, по крайней мере, снизить их негативное влияние.  
  
 Дополнительные проблемы рассматриваются в [вопросы и ответы](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md).  
  
## <a name="unsupported-standard-query-operators"></a>Неподдерживаемые стандартные операторы запросов  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает никакие методы стандартных операторов запросов (например, <xref:System.Linq.Enumerable.ElementAt%2A>). В результате компилируемых проектов могут по-прежнему возникать ошибки во время выполнения. Дополнительные сведения см. в разделе [преобразование стандартного оператора запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
## <a name="memory-issues"></a>Проблемы с использованием памяти  
 Если запрос использует находящуюся в памяти коллекцию и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>, запрос может быть выполнен в памяти, в зависимости от порядка, в котором указаны двух коллекций. Если запрос следует выполнить в памяти, извлекать данные из таблицы базы данных нет необходимости.  
  
 Этот способ неэффективен и может привести к потреблению значительных ресурсов памяти и процессора. Попытайтесь исключить подобные мультидоменные запросы.  
  
## <a name="file-names-and-sqlmetal"></a>Имена файлов и средство SQLMetal  
 Чтобы указать имя входного файла, добавьте имя в командную строку в качестве входного файла. Включение имени файла в строку подключения (параметром **/conn** ) не поддерживается. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="class-library-projects"></a>Проекты библиотеки классов  
 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] создает строку подключения в файле `app.config` проекта. Файл `app.config` не используется в проектах библиотек классов. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует строку соединения, заданную в файлах, созданных во время разработки. Изменение значения в `app.config` не приводит к изменениям базы данных, к которой подключается приложение.  
  
## <a name="cascade-delete"></a>Каскадное удаление  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любое из следующих действий.  
  
-   Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.  
  
-   Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.  
  
 В противном случае возникнет исключение <xref:System.Data.SqlClient.SqlException>.  
  
 Дополнительные сведения см. в разделе [как: удаление строк из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
## <a name="expression-not-queryable"></a>Выражение, не подходящее для запроса  
 Если вы получаете «выражение [выражение] незапрашиваемое; Возможно, отсутствует ссылка на сборку?» Ошибка, убедитесь, что из следующих действий:  
  
-   Приложение предназначено для выполнения в [!INCLUDE[compact_v35_short](../../../../../../includes/compact-v35-short-md.md)].  
  
-   Наличие ссылки на `System.Core.dll` и `System.Data.Linq.dll`.  
  
-   Наличие директивы `Imports` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) или `using` (C#) для <xref:System.Linq> и <xref:System.Data.Linq>.  
  
## <a name="duplicatekeyexception"></a>DuplicateKeyException  
 Во время отладки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта, можно переходить через отношения сущности. Таким образом этом элементы попадают в кэш, и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] становится их наличие. Если после этого предпринимается попытка выполнения метода <xref:System.Data.Linq.Table%601.Attach%2A>, или <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, или аналогичного, результатом которого являются несколько строк с одинаковым ключом, создается исключение <xref:System.Data.Linq.DuplicateKeyException>.  
  
## <a name="string-concatenation-exceptions"></a>Исключения при объединении строк  
 Объединение в операндах, сопоставленных с `[n]text` и другими `[n][var]char`, не поддерживается. При объединении строк, сопоставленных двум разным наборам типов, возникает исключение. Дополнительные сведения см. в разделе [методы System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md).  
  
## <a name="skip-and-take-exceptions-in-sql-server-2000"></a>Исключения методов "Skip" и "Take" в SQL Server 2000  
 При использовании <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> или <xref:System.Linq.Queryable.Take%2A> в базе данных SQL Server 2000 необходимо применять члены идентификации (<xref:System.Linq.Queryable.Skip%2A>) Запрос должен быть выполнен в одной таблице (без объединения) либо он должен представлять операцию <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> или <xref:System.Linq.Queryable.Union%2A> и не включать операцию <xref:System.Linq.Queryable.Concat%2A> operation. Дополнительные сведения см. в подразделе «Поддержка SQL Server 2000» [преобразование стандартного оператора запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
 Это требование не относится к [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
## <a name="groupby-invalidoperationexception"></a>GroupBy InvalidOperationException  
 Данное исключение возникает, если в запросе <xref:System.Linq.Enumerable.GroupBy%2A>, выполняющем группировку по выражению `boolean`, например `group x by (Phone==@phone)`, столбец имеет значение NULL. Поскольку выражение является `boolean`, ключ определяется как `boolean`, а не `nullable``boolean`. Если в результате преобразованного сравнения выводится значение null, предпринимается попытка назначить `nullable``boolean` для `boolean`, и исключение создается.  
  
 Чтобы избежать такой ситуации (предполагается, что значения NULL оцениваются как ложные), воспользуйтесь следующим способом.  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## <a name="oncreated-partial-method"></a>Разделяемый метод OnCreated()  
 Созданный метод `OnCreated()` вызывается при каждом вызове конструктора объектов, включая моменты, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывает его для копирования исходных значений. При реализации метода `OnCreated()` в собственном разделяемом классе данное поведение следует принять во внимание.  
  
## <a name="see-also"></a>См. также  
 [Поддержка отладки](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 [Часто задаваемые вопросы](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
