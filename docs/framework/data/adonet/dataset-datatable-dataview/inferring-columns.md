---
title: "Вывод столбцов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Вывод столбцов
ADO.NET определяет по XML\-документу, какие элементы выводятся как таблицы для <xref:System.Data.DataSet>, а затем выводятся столбцы для этих таблиц.  В ADO.NET 2.0 появился новый механизм вывода схемы, который выводит строго типизированный тип данных для каждого элемента **simpleType**.  В предыдущих версиях выводимый элемент **simpleType** всегда имел тип данных **xsd:string**.  
  
## Миграция и обратная совместимость  
 Метод **ReadXml** принимает в качестве аргумента тип **InferSchema**.  Этот аргумент позволяет задать поведение, совместимое с предыдущими версиями.  Допустимые значения для перечисления **InferSchema** приведены в следующей таблице.  
  
 <xref:System.Data.XmlReadMode>  
 Обеспечивает обратную совместимость, выводя в качестве простого типа всегда тип <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode>  
 Выводит строго типизированный тип данных.  Вызывает исключение при использовании с <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode>  
 Пропускает любую встроенную схему и считывает данные в существующую схему <xref:System.Data.DataSet>.  
  
## Атрибуты  
 Как определено в разделе [Вывод таблиц](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), элемент с атрибутами будет выведен как таблица.  Атрибуты этого элемента будут выведены как столбцы для таблицы.  Свойству **ColumnMapping** столбцов будет присвоено значение **MappingType.Attribute**, чтобы имена столбцов были записаны как атрибуты, если схема записывается обратно в XML.  Значения атрибутов хранятся в строке в таблице.  Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами, **attr1** и **attr2**.  Свойству **ColumnMapping** обоих столбцов будет присвоено значение **MappingType.Attribute**.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## Элементы без атрибутов или дочерние элементы  
 Если элемент не имеет дочерних элементов или атрибутов, то он будет выведен как столбец.  Свойству **ColumnMapping** столбца будет присвоено значение **MappingType.Element**.  Текст для дочерних элементов хранится в строке в таблице.  Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами, **ChildElement1** и **ChildElement2**.  Свойству **ColumnMapping** обоих столбцов будет присвоено значение **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## См. также  
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)