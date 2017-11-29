---
title: "Определение отношений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 41c73ac31105cdae0a23c2367211747dee8d44f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-relationships"></a>Определение отношений
Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>. Новый столбец с именем **ParentTableName_Id** будут добавлены в таблицу, созданную для родительского элемента и в таблицу, созданную для дочернего элемента. **ColumnMapping** будет присвоено свойству данного столбца идентификаторов **MappingType.Hidden**. Столбец будет с автоматическим приращением первичного ключа для родительской таблицы и будет использоваться для **DataRelation** между двумя таблицами. Тип данных добавленный столбец идентификаторов будет **System.Int32**, в отличие от типа данных всех остальных выведенных столбцов, который является **System.String**. Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule** = **Cascade** также будет создан с помощью нового столбца в родительской и дочерней таблицами.  
  
 Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Процесс вывода создаст две таблицы: **Element1** и **ChildElement1**.  
  
 **Element1** будет содержать два столбца: **Element1_Id** и **ChildElement2**. **ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**. **ColumnMapping** свойство **ChildElement2** столбца будет присвоено **MappingType.Element**. **Element1_Id** столбца будет установлено в качестве первичного ключа **Element1** таблицы.  
  
 **ChildElement1** будет содержать три столбца: **attr1**, **attr2** и **Element1_Id**. **ColumnMapping** свойство **attr1** и **attr2** столбцов будет присвоено **MappingType.Attribute**. **ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**.  
  
 Объект **DataRelation** и **ForeignKeyConstraint** будут созданы с использованием **Element1_Id** столбцы из обеих таблиц.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Таблица:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Вложенные:** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Столбец:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** None  
  
## <a name="see-also"></a>См. также  
 [Определение реляционной структуры набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Загрузка набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Загрузка сведений о схеме набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
