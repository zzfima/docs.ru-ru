---
title: "Выведение таблиц | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Выведение таблиц
При выведении схемы для <xref:System.Data.DataSet> из XML\-документа ADO.NET сначала определяет, какой из XML\-элементов представляет таблицы.  Следующие структуры XML приводятся в таблице для схемы **DataSet**.  
  
-   Элементы с атрибутами.  
  
-   Элементы с дочерними элементами.  
  
-   Повторяющиеся элементы.  
  
## Элементы с атрибутами  
 Элементы с заданными атрибутами приводятся в выведенных таблицах.  Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## Элементы с дочерними элементами  
 Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах.  Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов.  Если элемент документа не имеет атрибутов и дочерних элементов, которые можно вывести в виде столбцов, то элемент выводится в виде **DataSet**.  Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем DocumentElement.  
  
 **DataSet:** NewDataSet  
  
 **Table:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 В качестве альтернативы рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 В процессе вывода создается **DataSet** с именем DocumentElement, содержащий таблицу с именем Element1.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## Повторяющиеся элементы  
 Повторяющиеся элементы приводятся в выведенной таблице.  Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## См. также  
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)