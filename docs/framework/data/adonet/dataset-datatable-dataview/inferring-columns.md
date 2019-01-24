---
title: Определение столбцов
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: f3edd09b1fb8169e8f609514de38b3c37574079b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655235"
---
# <a name="inferring-columns"></a>Определение столбцов
ADO.NET определяет по XML-документу, какие элементы выводятся как таблицы для <xref:System.Data.DataSet>, а затем выводятся столбцы для этих таблиц. В ADO.NET 2.0 появился новый механизм вывода схемы, который выводит строго типизированный тип данных для каждого **simpleType** элемент. В предыдущих версиях выводимый тип данных **simpleType** элемент был всегда **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Миграция и обратная совместимость  
 **ReadXml** метод принимает аргумент типа **InferSchema**. Этот аргумент позволяет задать поведение, совместимое с предыдущими версиями. Доступные значения для **InferSchema** перечисления показаны в следующей таблице.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Обеспечивает обратную совместимость, выводя в качестве простого типа всегда тип <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Выводит строго типизированный тип данных. Вызывает исключение при использовании с <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Пропускает любую встроенную схему и считывает данные в существующую схему <xref:System.Data.DataSet>.  
  
## <a name="attributes"></a>Атрибуты  
 Как определено в [вывод таблиц](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), элемент с атрибутами будет выведен как таблица. Атрибуты этого элемента будут выведены как столбцы для таблицы. **ColumnMapping** свойства столбцов будет присвоено **MappingType.Attribute**, чтобы имена столбцов, которые будут записываться как атрибуты, если схема записывается обратно в XML. Значения атрибутов хранятся в строке в таблице. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами, **attr1** и **attr2**. **ColumnMapping** свойства обоих столбцов будет присвоено **MappingType.Attribute**.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Элементы без атрибутов или дочерние элементы  
 Если элемент не имеет дочерних элементов или атрибутов, то он будет выведен как столбец. **ColumnMapping** столбца будет установлено **MappingType.Element**. Текст для дочерних элементов хранится в строке в таблице. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами, **ChildElement1** и **ChildElement2**. **ColumnMapping** свойства обоих столбцов будет присвоено **MappingType.Element**.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>См. также
- [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
