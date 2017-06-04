---
title: "Устранение неполадок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Устранение неполадок
В данном материале представлен ряд проблем, которые могут возникнуть в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], и даны рекомендации, как их избежать или, по крайней мере, снизить их негативное влияние.  
  
 Решение других проблем рассматривается в разделе [Часто задаваемые вопросы](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md).  
  
## Неподдерживаемые стандартные операторы запросов  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает никакие методы стандартных операторов запросов \(например, <xref:System.Linq.Enumerable.ElementAt%2A>\).  В результате компилируемых проектов могут по\-прежнему возникать ошибки во время выполнения.  Для получения дополнительной информации см. [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
## Проблемы с использованием памяти  
 Если запрос использует находящуюся в памяти коллекцию и <xref:System.Data.Linq.Table%601> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], он может быть выполнен в памяти с учетом порядка указания двух коллекций.  Если запрос следует выполнить в памяти, извлекать данные из таблицы базы данных нет необходимости.  
  
 Этот способ неэффективен и может привести к потреблению значительных ресурсов памяти и процессора.  Попытайтесь исключить подобные мультидоменные запросы.  
  
## Имена файлов и средство SQLMetal  
 Чтобы указать имя входного файла, добавьте имя в командную строку в качестве входного файла.  Включение имени файла в строку подключения \(параметром **\/conn**\) не поддерживается.  Для получения дополнительной информации см. [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Проекты библиотеки классов  
 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] создает строку подключения в файле `app.config` проекта.  Файл `app.config` не используется в проектах библиотек классов.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует строку соединения, заданную в файлах, созданных во время разработки.  Изменение значения в `app.config` не приводит к изменениям базы данных, к которой подключается приложение.  
  
## Каскадное удаление  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления.  Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любое из следующих действий.  
  
-   Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.  
  
-   Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.  
  
 В противном случае возникнет исключение <xref:System.Data.SqlClient.SqlException>.  
  
 Для получения дополнительной информации см. [Как удалять строки из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
## Выражение, не подходящее для запроса  
 При получении ошибки «Выражение \[выражение\] незапрашиваемое; пропущена ссылка на сборку?» проверьте следующие условия.  
  
-   Приложение предназначено для выполнения в [!INCLUDE[compact_v35_short](../../../../../../includes/compact-v35-short-md.md)].  
  
-   Наличие ссылки на `System.Core.dll` и `System.Data.Linq.dll`.  
  
-   Наличие директивы `Imports` \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) или `using` \(C\#\) для <xref:System.Linq> и <xref:System.Data.Linq>.  
  
## DuplicateKeyException  
 Во время отладки проекта [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] можно переходить через отношения сущности.  При этом элементы попадают в кэш, и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет их наличие.  Если после этого предпринимается попытка выполнения метода <xref:System.Data.Linq.Table%601.Attach%2A>, или <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, или аналогичного, результатом которого являются несколько строк с одинаковым ключом, создается исключение <xref:System.Data.Linq.DuplicateKeyException>.  
  
## Исключения при объединении строк  
 Объединение в операндах, сопоставленных с `[n]text` и другими `[n][var]char`, не поддерживается.  При объединении строк, сопоставленных двум разным наборам типов, возникает исключение.  Для получения дополнительной информации см. [Методы System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md).  
  
## Исключения методов "Skip" и "Take" в SQL Server 2000  
 При использовании <xref:System.Linq.Queryable.Take%2A> или <xref:System.Linq.Queryable.Skip%2A> в базе данных SQL Server 2000 необходимо применять члены идентификации \(<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>\)  Запрос должен быть выполнен в одной таблице \(без объединения\) либо он должен представлять операцию <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> или <xref:System.Linq.Queryable.Union%2A> и не включать операцию <xref:System.Linq.Queryable.Concat%2A> operation.  Дополнительные сведения см. в подразделе "Поддержка SQL Server 2000" раздела [Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
 Это требование не относится к [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
## GroupBy InvalidOperationException  
 Данное исключение возникает, если в запросе <xref:System.Linq.Enumerable.GroupBy%2A>, выполняющем группировку по выражению `boolean`, например `group x by (Phone==@phone)`, столбец имеет значение NULL.  Поскольку выражение имеет тип `boolean`, ключ определяется как `boolean`, а не как `nullable` `boolean`.  Если в результате преобразованного сравнения выводится значение NULL, предпринимается попытка назначить `nullable` `boolean` для `boolean` и вызывается исключение.  
  
 Чтобы избежать такой ситуации \(предполагается, что значения NULL оцениваются как ложные\), воспользуйтесь следующим способом.  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## Разделяемый метод OnCreated\(\)  
 Созданный метод `OnCreated()` вызывается при каждом вызове конструктора объектов, включая моменты, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывает его для копирования исходных значений.  При реализации метода `OnCreated()` в собственном разделяемом классе данное поведение следует принять во внимание.  
  
## См. также  
 [Поддержка отладки](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)   
 [Часто задаваемые вопросы](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)