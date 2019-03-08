---
title: ограничение ссылочной целостности
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 7d3304393ef4e97887d9b8afec94ed265e38eaf0
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679116"
---
# <a name="referential-integrity-constraint"></a>ограничение ссылочной целостности
Объект *ограничение ссылочной целостности* в Entity Data Model (EDM) аналогичен ограничения ссылочной целостности в реляционной базе данных. Таким же образом, столбец или столбцы из таблицы базы данных можно ссылаться на первичный ключ другой таблицы [свойство](../../../../docs/framework/data/adonet/property.md) (или свойства) из [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) могут ссылаться на [ключ сущности ](../../../../docs/framework/data/adonet/entity-key.md) другого типа сущности. Тип сущности, на который приведена ссылка называется *основного конца* ограничения. Тип сущности, который ссылается на основном конечном элементе называется *зависимого конца* ограничения.  
  
 Ограничение ссылочной целостности определяется как часть [ассоциации](../../../../docs/framework/data/adonet/association-type.md) между двумя типами сущностей. Определение ограничения ссылочной целостности включает следующую информацию.  
  
-   Основной конец ограничения. (Тип сущности, ключ сущности которого имеет ссылку на зависимый конец.)  
  
-   Ключ сущности основного конца.  
  
-   Зависимый конец ограничения. (Тип сущности, который имеет свойство или свойства, ссылающиеся на ключ сущности основного конца.)  
  
-   Ссылка на свойство или свойства зависимого конца.  
  
 Целью ограничения ссылочной целостности в модели EDM является обеспечение постоянного существования допустимых ассоциаций. Дополнительные сведения см. в разделе [свойство внешнего ключа](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`. Тип сущности `Book` имеет свойство `PublisherId`, которое ссылается на ключ сущности типа сущности `Publisher` при определении ограничения ссылочной целостности ассоциации `PublishedBy`.  
  
 ![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "пример модели справочное ограничение")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее на языке CSDL определяется ограничение ссылочной целостности для ассоциации `PublishedBy`, которая ранее приводилась в концептуальной модели.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>См. также
- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
