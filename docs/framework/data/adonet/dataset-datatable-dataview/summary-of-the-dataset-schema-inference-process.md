---
title: "Сводка процесса вывода схемы DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сводка процесса вывода схемы DataSet
Процесс вывода схемы из XML\-документа вначале определяет, какие элементы будут выведены как таблицы.  Из оставшегося XML процесс вывода схемы определяет столбцы этих таблиц.  Для вложенных таблиц процесс вывода формирует вложенные объекты <xref:System.Data.DataRelation> и <xref:System.Data.ForeignKeyConstraint>.  
  
 Далее представлена краткая сводка правил вывода.  
  
-   Элементы с атрибутами выводятся как таблицы.  
  
-   Элементы, имеющие дочерние элементы, выводятся как таблицы.  
  
-   Повторяющиеся элементы выводятся как одна таблица.  
  
-   Если элемент документа \(корневой элемент\) не имеет ни атрибутов, ни дочерних элементов, которые выводились бы как столбцы, он выводится как <xref:System.Data.DataSet>.  В противном случае элемент документа выводится как таблица.  
  
-   Атрибуты выводятся как столбцы.  
  
-   Элементы, которые не повторяются и не имеют ни атрибутов, ни дочерних элементов, выводятся как столбцы.  
  
-   Для элементов, которые выводятся как таблицы, вложенные в другие элементы, которые также выводятся как таблицы, между двумя таблицами создается вложенный элемент **DataRelation**.  Новый столбец первичного ключа с именем **TableName\_Id** добавляется к обеим таблицам и используется элементом **DataRelation**.  Между двумя таблицами создается элемент **ForeignKeyConstraint** с использованием столбца **TableName\_Id**.  
  
-   Для элементов, которые выводятся как таблицы и содержат текст, но не имеют дочерних элементов, создается новый столбец с именем **TableName\_Text** для текста каждого из таких элементов.  Если элемент выводится как таблица и имеет текст, но при этом имеет дочерние элементы, текст пропускается.  
  
## См. также  
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)