---
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: f777b225f9fbf4e8ce38778842d30a0a3054e22a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573505"
---
# <a name="inferring-tables"></a>Определение таблиц
При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы. Следующие структуры XML приводятся в таблице для **набора данных** схемы:  
  
-   Элементы с атрибутами.  
  
-   Элементы с дочерними элементами.  
  
-   Повторяющиеся элементы.  
  
## <a name="elements-with-attributes"></a>Элементы с атрибутами  
 Элементы с заданными атрибутами приводятся в выведенных таблицах. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## <a name="elements-with-child-elements"></a>Элементы с дочерними элементами  
 Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов. Если элемент документа не имеет атрибутов и дочерних элементов, которые выводились бы как столбцы, то элемент выводится как **набора данных**. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем DocumentElement.  
  
 **Набор данных:** NewDataSet  
  
 **Таблица:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 В качестве альтернативы рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 В процессе вывода создается **набора данных** с именем «DocumentElement», который содержит таблицу с именем «Элемент1».  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="repeating-elements"></a>Повторяющиеся элементы  
 Повторяющиеся элементы приводятся в выведенной таблице. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>См. также
- [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
