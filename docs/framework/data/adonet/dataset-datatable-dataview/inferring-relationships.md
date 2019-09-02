---
title: Определение отношений
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 92a4953dc7f5119ffbf171ff2a7bf5b58e896638
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204769"
---
# <a name="inferring-relationships"></a>Определение отношений
Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>. Новый столбец с именем **ParentTableName_Id** будет добавлен как в таблицу, созданную для родительского элемента, так и на таблицу, созданную для дочернего элемента. Свойству **ColumnMapping** этого столбца идентификаторов будет присвоено значение **MappingType. Hidden**. Столбец будет автоматически инкрементным первичным ключом для родительской таблицы и будет использоваться для **связи DataRelation** между двумя таблицами. Тип данных добавленного столбца идентификаторов будет **System. Int32**, в отличие от типа данных всех других выводимых столбцов, которые имеют тип **System. String**. Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule** = **CASCADE** также будет создан с помощью нового столбца как в родительской, так и в дочерней таблице.  
  
 Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 В процессе вывода будут созданы две таблицы: **Element1** и **ChildElement1**.  
  
 Таблица **Element1** будет содержать два столбца: **Element1_Id** и **ChildElement2**. Свойству **ColumnMapping** столбца **Element1_Id** будет присвоено значение **MappingType. Hidden**. Свойству **ColumnMapping** столбца **ChildElement2** будет присвоено значение **MappingType. element**. Столбец **Element1_Id** будет установлен в качестве первичного ключа таблицы **Element1** .  
  
 Таблица **ChildElement1** будет содержать три столбца: **attr1**, **attr2** и **Element1_Id**. Свойству **ColumnMapping** для столбцов **attr1** и **attr2** будет присвоено значение **MappingType. Attribute**. Свойству **ColumnMapping** столбца **Element1_Id** будет присвоено значение **MappingType. Hidden**.  
  
 **DataRelation** и **ForeignKeyConstraint** будут созданы с использованием столбцов **Element1_Id** из обеих таблиц.  
  
 **Объекте** DocumentElement  
  
 **Таблица** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Таблица** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation** Element1_ChildElement1  
  
 **Паренттабле:** Element1  
  
 **Парентколумн:** Element1_Id  
  
 **ChildTable** ChildElement1  
  
 **Чилдколумн:** Element1_Id  
  
 **Вложенные** True  
  
 **ForeignKeyConstraint** Element1_ChildElement1  
  
 **Рубрик** Element1_Id  
  
 **Паренттабле:** Element1  
  
 **ChildTable** ChildElement1  
  
 **DeleteRule** Cascade  
  
 **Акцептрежектруле:** Отсутствуют  
  
## <a name="see-also"></a>См. также

- [Определение реляционной структуры DataSet из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка DataSet из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме DataSet из XML](loading-dataset-schema-information-from-xml.md)
- [Вложенность объектов DataRelation](nesting-datarelations.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
