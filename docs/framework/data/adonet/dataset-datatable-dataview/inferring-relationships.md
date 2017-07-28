---
title: "Выведение связей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Выведение связей
Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>.  В таблицу, созданную для родительского элемента, и в таблицу, созданную для дочернего элемента, будет добавлен новый столбец **ParentTableName\_Id**.  Свойству **ColumnMapping** этого столбца идентификаторов будет задано значение **MappingType.Hidden**.  Этот столбец будет первичным ключом с автоматическим приращением для родительской таблицы и будет использоваться для связи **DataRelation** между двумя таблицами.  Добавленный столбец идентификаторов будет иметь тип данных **System.Int32**, в отличие от типа данных всех остальных выведенных столбцов, а именно **System.String**.  При помощи нового столбца в родительской и дочерней таблицах также будет создано ограничение <xref:System.Data.ForeignKeyConstraint> с **DeleteRule** \= **Cascade**.  
  
 Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Процесс вывода создаст две таблицы: **Element1** и **ChildElement1**.  
  
 Таблица **Element1** будет содержать два столбца: **Element1\_Id** и **ChildElement2**.  Свойству **ColumnMapping** столбца **Element1\_Id** будет установлено значение **MappingType.Hidden**.  Свойству **ColumnMapping** столбца **ChildElement2** будет установлено значение **MappingType.Element**.  Столбец **Element1\_Id** будет задан в качестве первичного ключа таблицы **Element1**.  
  
 Таблица **ChildElement1** будет содержать три столбца: **attr1**, **attr2** и **Element1\_Id**.  Свойству **ColumnMapping** столбцов **attr1** и **attr2** будет установлено значение **MappingType.Attribute**.  Свойству **ColumnMapping** столбца **Element1\_Id** будет установлено значение **MappingType.Hidden**.  
  
 Связь **DataRelation** и ограничение **ForeignKeyConstraint** будут созданы при помощи столбцов **Element1\_Id** обеих таблиц.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1\_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Table:** ChildElement1  
  
|attr1|attr2|Element1\_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1\_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1\_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1\_Id  
  
 **Nested:** True  
  
 **ForeignKeyConstraint:** Element1\_ChildElement1  
  
 **Column:** Element1\_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** None  
  
## См. также  
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Вложенность объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)