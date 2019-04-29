---
title: Семантика сравнения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605975"
---
# <a name="comparison-semantics-entity-sql"></a>Семантика сравнения (Entity SQL)
Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.  
  
## <a name="explicit-comparison"></a>Явное сравнение  
 Операции сравнения:  
  
- =  
  
- !=  
  
 Операции упорядочивания:  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 Операции допустимости значений NULL:  
  
- IS NULL  
  
- IS NOT NULL  
  
## <a name="explicit-distinction"></a>Явное отличие  
 Отличие равенства:  
  
- DISTINCT  
  
- GROUP BY  
  
 Отличие упорядочивания:  
  
- ORDER BY  
  
## <a name="implicit-distinction"></a>Неявное отличие  
 Операция и предикаты для работы с наборами (равенство):  
  
- UNION  
  
- INTERSECT  
  
- EXCEPT  
  
- SET  
  
- OVERLAPS  
  
 Предикаты элементов (равенство):  
  
- IN  
  
## <a name="supported-combinations"></a>Поддерживаемые сочетания  
 В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.  
  
|**Type**|**=**<br /><br /> **\!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**ИМЕЕТ ЗНАЧЕНИЕ NULL**<br /><br /> **НЕ РАВНО NULL**|  
|-|-|-|-|-|-|-|-|  
|Тип сущности|Ref<sup>1</sup>|Все свойства<sup>2</sup>|Все свойства<sup>2</sup>|Все свойства<sup>2</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Ref<sup>1</sup>|  
|Сложный тип|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|  
|Строка|Все свойства<sup>4</sup>|Все свойства<sup>4</sup>|Все свойства<sup>4</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Все свойства<sup>4</sup>|Исключение<sup>3</sup>|  
|Тип-примитив|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|  
|Мультинабор|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|  
|Ссылочный|Да<sup>5</sup>|Да<sup>5</sup>|Да<sup>5</sup>|Да<sup>5</sup>|Throw|Throw|Да<sup>5</sup>|  
|Ассоциация<br /><br /> type|Исключение<sup>3</sup>|Throw|Throw|Throw|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|  
  
 <sup>1</sup>ссылки экземпляров типа сущности неявно сравниваются, как показано в следующем примере:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Экземпляр сущности нельзя сравнивать с явной ссылкой. При попытке такого сравнения возникнет исключение. Например, следующий запрос вызовет исключение:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>свойства сложных типов выравниваются перед отправкой в хранилище, поэтому их можно сравнивать (при условии, что сравнимы их свойства). Также см. в разделе <sup>4.</sup>  
  
 <sup>3</sup>среды выполнения платформы Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.  
  
 <sup>4</sup>сделана попытка сравнить все свойства. Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.  
  
 <sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства типа сущности).  
  
## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
