---
title: "Определение схемы DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Определение схемы DataTable
Схема, или структура, таблицы представляется столбцами и ограничениями.  Схема <xref:System.Data.DataTable> определяется с использованием объектов <xref:System.Data.DataColumn>, а также объектов <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>.  Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.  
  
 В ссылках по имени на столбцы, связи и ограничения таблицы учитывается регистр.  Поэтому в таблице могут существовать столбцы, связи и ограничения, имеющие одинаковое имя, но отличающиеся регистром.  Например, могут быть столбцы **Col1** и **col1**.  В таком случае ссылка на один из столбцов по имени должна точно соответствовать регистру столбца; в противном случае возникает исключение.  Например, если таблица **myTable** содержит столбцы **Col1** и **col1**, ссылка по имени на **Col1** выполняется как **myTable.Columns\["Col1"\]**, а на **col1** \- как **myTable.Columns\["col1"\]**.  Попытка ссылки на какой\-либо из столбцов как **myTable.Columns\["COL1"\]** создаст исключение.  
  
 Правило учета регистра не применяется, если существует только один столбец, одна связь или ограничение с конкретным именем.  Это означает, что если в таблице нет другого объекта столбца, связи или ограничения, имя которого совпадает с именем этого конкретного объекта столбца, связи или ограничения, то на объект можно ссылаться по имени, используя любой регистр, и исключение в этом случае не возникает.  Например, если таблица имеет только столбец **Col1**, на него можно ссылаться с использованием **my.Columns\["COL1"\]**.  
  
> [!NOTE]
>  Свойство <xref:System.Data.DataTable.CaseSensitive%2A> таблицы **DataTable** не влияет на это поведение.  Свойство **CaseSensitive** применяется к данным в таблице и влияет на сортировку, поиск, фильтрацию, принудительное выполнение ограничений и т. д., но не на ссылки на столбцы, связи и ограничения.  
  
## В этом подразделе  
 [Добавление столбцов к DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Описывает, как определить столбцы таблицы с использованием объектов **DataColumn**.  
  
 [Создание столбцов выражений](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Поясняет, как свойство **Expression** столбца может использоваться для расчета значений на основании значений из других столбцов в строке.  
  
 [Создание столбцов AutoIncrement](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Описывает, как для столбца может быть установлено автоматическое увеличение числовых значений для обеспечения уникального значения столбца в строке.  
  
 [Определение первичных ключей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Описывает, как задать первичный ключ таблицы по одному или нескольким объектам **DataColumn**.  
  
 [Ограничения DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Описывает, как определить внешний ключ и ограничения уникальности для столбцов в таблице.  
  
## См. также  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)