---
title: "Семантика сравнения (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2835d2064f1845b55dd3a33abb086c5af0fb9e6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="comparison-semantics-entity-sql"></a>Семантика сравнения (Entity SQL)
Выполнение любого следующего оператора [!INCLUDE[esql](../../../../../../includes/esql-md.md)] подразумевает сравнение типов экземпляров.  
  
## <a name="explicit-comparison"></a>Явное сравнение  
 Операции сравнения:  
  
-   =  
  
-   !=  
  
 Операции упорядочивания:  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 Операции допустимости значений NULL:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## <a name="explicit-distinction"></a>Явное отличие  
 Отличие равенства:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 Отличие упорядочивания:  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>Неявное отличие  
 Операция и предикаты для работы с наборами (равенство):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 Предикаты элементов (равенство):  
  
-   IN  
  
## <a name="supported-combinations"></a>Поддерживаемые сочетания  
 В следующей таблице приводятся все поддерживаемые сочетания операторов сравнения для каждого типа.  
  
|**Type**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**ИМЕЕТ ЗНАЧЕНИЕ NULL**<br /><br /> **НЕ ИМЕЕТ ЗНАЧЕНИЕ NULL**|  
|-|-|-|-|-|-|-|-|  
|Тип сущности|Ref<sup>1</sup>|Все свойства<sup>2</sup>|Все свойства<sup>2</sup>|Все свойства<sup>2</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Ref<sup>1</sup>|  
|Сложный тип|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|  
|Строка|Все свойства<sup>4</sup>|Все свойства<sup>4</sup>|Все свойства<sup>4</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Все свойства<sup>4</sup>|Исключение<sup>3</sup>|  
|Тип-примитив|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|Зависит от поставщика|  
|Мультинабор|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|  
|Ссылочный|Да<sup>5</sup>|Да<sup>5</sup>|Да<sup>5</sup>|Да<sup>5</sup>|Throw|Throw|Да<sup>5</sup>|  
|Ассоциация<br /><br /> type|Исключение<sup>3</sup>|Throw|Throw|Throw|Исключение<sup>3</sup>|Исключение<sup>3</sup>|Исключение<sup>3</sup>|  
  
 <sup>1</sup>ссылки на тип экземпляров данной сущности неявно сравниваются, как показано в следующем примере:  
  
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
  
 <sup>2</sup>свойства сложных типов выравниваются перед его отправкой в хранилище, поэтому они станут сопоставимых (поскольку сравнимы их свойства). См. также <sup>4.</sup>  
  
 <sup>3</sup>выполнения платформа Entity Framework обнаруживает неподдерживаемый вариант и вызывает значимое исключение, не вовлекая поставщик или хранилище.  
  
 <sup>4</sup>попытка сравнить все свойства. Если имеется свойство несравнимого типа, например text, ntext или image, может возникнуть серверное исключение.  
  
 <sup>5</sup>сравниваются все отдельные элементы ссылок (включая имя набора сущностей и все ключевые свойства этого типа сущности).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
