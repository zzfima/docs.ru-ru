---
title: "Как создать модель объектов на языке Visual Basic или C# | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как создать модель объектов на языке Visual Basic или C# #
В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектная модель используемого языка программирования сопоставляется с реляционной базой данных.  Для автоматического создания модели языка [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C\# из метаданных существующей базы данных предусмотрено два средства.  
  
-   При работе в среде [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] для создания объектной модели можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  Конструктор [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] предоставляет развитый пользовательский интерфейс для создания объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Средство командной строки SQLMetal.  Дополнительные сведения см. в разделе [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    >  Если существующие базы данных отсутствуют и необходимо создать базу данных из объектной модели, можно создать объектную модель с помощью редактора кода и метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.  Дополнительные сведения см. в разделе [Как динамически создать базу данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
 В документации по конструктору [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] приводятся примеры создания объектных моделей на языке [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C\# с помощью конструктора [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].  Ниже приведены примеры использования программы командной строки SQLMetal.  Дополнительные сведения см. в разделе [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Пример  
 С помощью команды программы SQLMetal, представленной в следующем примере, создается код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] для основанной на атрибутах объектной модели базы данных "Northwind".  Также отображаются хранимые процедуры и функции.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## Пример  
 С помощью команды программы SQLMetal, представленной в следующем примере, создается код C\# для основанной на атрибутах объектной модели базы данных "Northwind".  Также отображаются хранимые процедуры и функции и имена таблиц автоматически преобразуются в имена во множественном числе.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## См. также  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)   
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Обучение с помощью пошаговых руководств](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)   
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)   
 [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)   
 [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)   
 [Внешние сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)