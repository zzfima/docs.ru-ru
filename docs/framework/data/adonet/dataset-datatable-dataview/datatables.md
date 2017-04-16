---
title: "DataTables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTables
Набор данных <xref:System.Data.DataSet> состоит из коллекции таблиц, связей и ограничений.  В ADO.NET объекты <xref:System.Data.DataTable> используются для представления таблиц в наборе данных **DataSet**.  Таблица данных **DataTable** представляет одну таблицу с реляционными данными, размещенными в памяти. Данные локально расположены в приложении на основе .NET, но могут заполняться из источника данных, например Microsoft SQL Server, с помощью **DataAdapter**. Дополнительные сведения см. в разделе [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).  
  
 Класс **DataTable** является элементом пространства имен **System.Data** внутри библиотеки классов платформы .NET Framework.  Можно создавать и использовать **DataTable** независимо или в качестве элемента **DataSet**, и объекты **DataTable** также можно использовать совместно с другими объектами платформы .NET Framework, включая <xref:System.Data.DataView>.  Доступ к коллекции таблиц в **DataSet** обеспечивается с помощью свойства **Tables** объекта **DataSet**.  
  
 Схема или структура таблицы представляется столбцами и ограничениями.  Схема **DataTable** определяется с помощью объектов <xref:System.Data.DataColumn>, а также объектов <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>.  Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.  
  
 Кроме схемы, объект **DataTable** должен также иметь строки, в которых хранятся и упорядочиваются данные.  Класс <xref:System.Data.DataRow> представляет фактические данные, содержащиеся в таблице.  Объект **DataRow**, а также его свойства и методы используются для извлечения, оценки и обработки данных таблицы.  После доступа к данным строки и их изменения объект **DataRow** сохраняет и текущее, и исходное состояние.  
  
 С помощью одного или нескольких связанных столбцов таблицы между таблицами можно создавать связи типа «родители\-потомки».  Связь между объектами **DataTable** создается с помощью <xref:System.Data.DataRelation>.  Объекты **DataRelation** можно использовать для возврата связанных дочерних или родительских строк определенной строки.  Для получения дополнительной информации см. [Добавление объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## В этом подразделе  
 [Создание DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Объясняет, как создавать **DataTable** и добавлять ее в **DataSet**.  
  
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Содержит сведения о создании и использовании объектов и ограничений **DataColumn**.  
  
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Описывает, как добавлять, изменять и удалять данные таблицы.  Объясняет, как использовать события **DataTable** для изучения изменений данных таблицы.  
  
 [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Приводит сведения о событиях, которые можно использовать с объектом **DataTable**, включая события, связанные с изменением значений столбцов и добавлением или удалением строк.  
  
## Связанные подразделы  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Описывает архитектуру и компоненты ADO.NET, а также их использование для получения доступа к существующим источникам данных и управления данными приложения.  
  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Содержит сведения о классе **DataSet** ADO.NET, в том числе о способе создания связей между таблицами.  
  
 [Класс Constraint](frlrfSystemDataConstraintClassTopic)  
 Предоставляет справочные сведения об объекте **Constraint**.  
  
 [Класс DataColumn](frlrfSystemDataDataColumnClassTopic)  
 Содержит справочные сведения об объекте **DataColumn**.  
  
 [Класс DataSet](frlrfSystemDataDataSetClassTopic)  
 Содержит справочные сведения об объекте **DataSet**.  
  
 [Класс DataTable](frlrfSystemDataDataTableClassTopic)  
 Содержит справочные сведения об объекте **DataTable**.  
  
 [Общие сведения о библиотеке классов](../../../../../docs/standard/class-library-overview.md)  
 Содержит общие сведения о библиотеке классов платформы .NET Framework, включая пространство имен **System**, а также пространство имен второго уровня, **System.Data**.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)