---
title: Система типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: b8b721aff5b7886fdb897ecaa3dcc163ec94ae79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149835"
---
# <a name="type-system-entity-sql"></a>Система типов (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]поддерживает ряд типов:  
  
- Типы-примитивы (простые типы), такие как `Int32` и `String.`  
  
- Номинальные типы, которые определяются в схеме, например <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> и <xref:System.Data.Metadata.Edm.RelationshipType>.  
  
- Анонимные типы, которые явно не определяются в схеме: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> и <xref:System.Data.Metadata.Edm.RefType>.  
  
 В этом разделе рассматриваются анонимные типы, которые не определены в схеме явно, но поддерживаются Entity S'L. Для получения информации о примитивных и номинальных типах [см.](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)  
  
## <a name="rows"></a>Строки  
 Структура строки зависит от последовательности типизированных и именованных элементов, из которых состоит строка. Тип строки не имеет идентификатора и не может наследоваться. Экземпляры строк одинакового типа считаются равными, если равны соответствующие элементы этих строк. Со строками не связаны операции, отличные от проверки равнозначности их структуры, к тому же они не имеют эквивалентов в среде CLR. Запросы могут возвращать структуры, содержащие строки или коллекции строк. API определения привязки между запросами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] и базовым языком определяет способ реализации строк в запросе, вырабатывающем этот результат. Для получения информации о том, как построить экземпляр [строки, см.](constructing-types-entity-sql.md)  
  
## <a name="collections"></a>Коллекции  
 Типы коллекций представляют ноль и более экземпляров других объектов. Для получения [информации](constructing-types-entity-sql.md)о том, как построить сбор, см.  
  
## <a name="references"></a>Ссылки  
 Ссылка - это логический указатель на отдельную сущность в определенном наборе сущностей.  
  
 Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает следующие операторы для конструирования, деконструирования и перехода по ссылкам.  
  
- [Ref](ref-entity-sql.md)  
  
- [CREATEREF](createref-entity-sql.md)  
  
- [Ключ](key-entity-sql.md)  
  
- [DEREF](deref-entity-sql.md)  
  
 По ссылке можно переходить с помощью оператора доступа к элементам «точка» (`.`). В следующем фрагменте извлекается свойство Id (объекта Order) путем перехода по свойству r (сокращение от reference).  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 Если ссылка имеет значение NULL или цель ссылки не существует, результатом становится NULL.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об Entity SQL](entity-sql-overview.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
- [CAST](cast-entity-sql.md)
- [Спецификации CSDL, SSDL и MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
