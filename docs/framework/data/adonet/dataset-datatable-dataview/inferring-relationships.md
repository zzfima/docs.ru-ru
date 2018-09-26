---
title: Определение отношений
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193178"
---
# <a name="inferring-relationships"></a>Определение отношений
Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>. Новый столбец с именем **ParentTableName_Id** будут добавлены как таблицы, созданной для родительского элемента, так и таблицу, созданную для дочернего элемента. **ColumnMapping** данного столбца идентификаторов будет установлено **MappingType.Hidden**. Столбец будет заданы с автоматическим приращением первичным ключом для родительской таблицы, а также будет использоваться для **DataRelation** между двумя таблицами. Тип данных добавленный столбец идентификаторов будет **System.Int32**, в отличие от всех остальных выведенных столбцов типа данных, который является **System.String**. Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule** = **Cascade** также будет создаваться с помощью нового столбца в родительской и дочерней таблицами.  
  
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
  
 **Element1** таблица будет содержать два столбца: **Element1_Id** и **ChildElement2**. **ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**. **ColumnMapping** свойство **ChildElement2** столбца будет присвоено **MappingType.Element**. **Element1_Id** столбца будет установлено в качестве первичного ключа **Element1** таблицы.  
  
 **ChildElement1** таблица будет иметь три столбца: **attr1**, **attr2** и **Element1_Id**. **ColumnMapping** свойство для **attr1** и **attr2** столбцов будет присвоено **MappingType.Attribute**. **ColumnMapping** свойство **Element1_Id** столбца будет присвоено **MappingType.Hidden**.  
  
 Объект **DataRelation** и **ForeignKeyConstraint** будет создан с помощью **Element1_Id** столбцы из обеих таблиц.  
  
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
 [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Вложенность объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
