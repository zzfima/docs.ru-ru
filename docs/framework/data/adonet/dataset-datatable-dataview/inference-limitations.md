---
title: "Ограничения на вывод | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Ограничения на вывод
Процесс вывода схемы <xref:System.Data.DataSet> из XML\-кода может приводиться в различных схемах в зависимости от XML\-элементов в каждом документе.  Например, рассмотрим следующие XML\-документы.  
  
 Document1:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Из\-за того, что Element1 является повторяющимся элементом, для Document1 процесс вывода производит **DataSet** с именем DocumentElement и таблицу с именем Element1.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Однако для Document2 процесс вывода производит **DataSet** с именем NewDataSet и таблицу с именем DocumentElement. Element1 выводится в виде столбца, потому что не имеет атрибутов и дочерних элементов.  
  
 **DataSet:** NewDataSet  
  
 **Table:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Эти два XML\-документа, возможно, должны были выдавать одну и ту же схему, но процесс вывода дает значительно различающиеся результаты в зависимости от элементов, содержащихся в каждом документе.  
  
 Во избежание несоответствий, которые могут произойти при создании схемы из XML\-документа, при загрузке **набора данных** из XML\-кода рекомендуется явно задавать схему с помощью языка XSD или языка XDR.  Дополнительные сведения о явном задании схемы **DataSet** с помощью схемы XML см. в разделе [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## См. также  
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)