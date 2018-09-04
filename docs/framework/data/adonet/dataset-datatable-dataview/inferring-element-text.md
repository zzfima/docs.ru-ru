---
title: Определение текста элемента
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: b70f76d2702ebcb098c64ea84900b723fbc137ab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516498"
---
# <a name="inferring-element-text"></a>Определение текста элемента
Если элемент содержит текст и не имеет дочерних элементов был определен как таблицы, например (элементы с атрибутами) или повторяющимися элементами, новый столбец с именем **TableName_Text** добавляется к таблице, выводящейся для элемента. Текст, содержащийся в элементе, будет добавлен в строку таблицы и сохранен в новом столбце. **ColumnMapping** нового столбца будет установлено **MappingType.SimpleContent**.  
  
 Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами: **attr1** и **Element1_Text**. **ColumnMapping** свойство **attr1** столбца будет присвоено **MappingType.Attribute**. **ColumnMapping** свойство **Element1_Text** столбца будет присвоено **MappingType.SimpleContent**.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Если элемент содержит текст, а также имеет дочерние элементы, содержащие текст, столбец не будет добавлен в таблицу для хранения текста, содержащегося в элементе. Текст, содержащийся в элементе, пропускается, а текст в дочерних элементах включается в строку таблицы. Например, рассмотрим следующий XML-код:  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 Процесс вывода сформирует таблицу с именем **Element1** с одним столбцом с именем **ChildElement1**. Текст для **ChildElement1** элемент будет включен в строку в таблице. Весь прочий текст будет пропущен. **ColumnMapping** свойство **ChildElement1** столбца будет присвоено **MappingType.Element**.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>См. также  
 [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
