---
title: "Выведение текста элементов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Выведение текста элементов
Если элемент, содержащий текст и не имеющий дочерних элементов, выводится в виде таблиц \(например, в виде элементов с атрибутами или повторяющимися элементами\), то к таблице, выводящейся для элемента, будет добавлен новый столбец с именем **TableName\_Text**.  Текст, содержащийся в элементе, будет добавлен в строку таблицы и сохранен в новом столбце.  Свойству **ColumnMapping** нового столбца будет установлено значение **MappingType.SimpleContent**.  
  
 Например, рассмотрим следующий XML\-код:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами: **attr1** и **Element1\_Text**.  Свойству **ColumnMapping** столбца **attr1** будет установлено значение **MappingType.Attribute**.  Свойству **ColumnMapping** столбца **Element1\_Text** будет установлено значение **MappingType.SimpleContent**.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Если элемент содержит текст, а также имеет дочерние элементы, содержащие текст, столбец не будет добавлен в таблицу для хранения текста, содержащегося в элементе.  Текст, содержащийся в элементе, пропускается, а текст в дочерних элементах включается в строку таблицы.  Например, рассмотрим следующий XML\-код:  
  
```  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** и одним столбцом с именем **ChildElement1**.  Текст для элемента **ChildElement1** будет включен в строку таблицы.  Весь прочий текст будет пропущен.  Свойству **ColumnMapping** столбца **ChildElement1** будет установлено значение **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## См. также  
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)