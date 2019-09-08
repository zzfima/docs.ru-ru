---
title: Определение столбцов
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 2718cbcf29799f99c8648b129fdb6079a6f6d344
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786175"
---
# <a name="inferring-columns"></a>Определение столбцов
ADO.NET определяет по XML-документу, какие элементы выводятся как таблицы для <xref:System.Data.DataSet>, а затем выводятся столбцы для этих таблиц. В ADO.NET 2,0 появился новый механизм вывода схемы, который выводит строго типизированный тип данных для каждого элемента **simpleType** . В предыдущих версиях тип данных выводимого элемента **simpleType** всегда имеет значение **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Миграция и обратная совместимость  
 Метод **ReadXml** принимает аргумент типа **инферсчема**. Этот аргумент позволяет задать поведение, совместимое с предыдущими версиями. Доступные значения перечисления **инферсчема** показаны в следующей таблице.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Обеспечивает обратную совместимость, выводя в качестве простого типа всегда тип <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Выводит строго типизированный тип данных. Вызывает исключение при использовании с <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Пропускает любую встроенную схему и считывает данные в существующую схему <xref:System.Data.DataSet>.  
  
## <a name="attributes"></a>Атрибуты  
 Как определено в [выведение таблиц](inferring-tables.md), элемент с атрибутами будет выведен как таблица. Атрибуты этого элемента будут выведены как столбцы для таблицы. Свойству **ColumnMapping** столбцов будет присвоено значение **MappingType. Attribute**, чтобы гарантировать, что имена столбцов будут записаны как атрибуты, если схема записывается обратно в XML. Значения атрибутов хранятся в строке в таблице. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем **Element1** с двумя столбцами, **attr1** и **attr2**. Свойство **ColumnMapping** обоих столбцов будет иметь значение **MappingType. Attribute**.  
  
 **Объекте** DocumentElement  
  
 **Таблица** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Элементы без атрибутов или дочерние элементы  
 Если элемент не имеет дочерних элементов или атрибутов, то он будет выведен как столбец. Свойству **ColumnMapping** столбца будет присвоено значение **MappingType. element**. Текст для дочерних элементов хранится в строке в таблице. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем **Element1** с двумя столбцами, **ChildElement1** и **ChildElement2**. Свойство **ColumnMapping** обоих столбцов будет иметь значение **MappingType. element**.  
  
 **Объекте** DocumentElement  
  
 **Таблица** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>См. также

- [Определение реляционной структуры DataSet из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка DataSet из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме DataSet из XML](loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
