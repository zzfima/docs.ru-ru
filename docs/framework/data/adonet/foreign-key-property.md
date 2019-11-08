---
title: свойство внешнего ключа
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: a77f7479ce38cb34830377021157f312916baca4
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738396"
---
# <a name="foreign-key-property"></a>свойство внешнего ключа
*Свойство внешнего ключа* в EDM (EDM) является [свойством](property.md) типа-примитива (или набором свойств типа-примитива) для [типа сущности](entity-type.md) , который содержит [ключ сущности](entity-key.md) другого типа сущности.  
  
 Свойство внешнего ключа схоже со столбцом внешнего ключа в реляционной базе данных. Так же, как внешние ключевые столбцы используются в реляционной базе данных для создания связей между строками в таблицах, свойства внешнего ключа в концептуальной модели используются для установления [связей](association-type.md) между типами сущностей. [Ограничение ссылочной целостности](referential-integrity-constraint.md) используется для определения ассоциации между двумя типами сущностей, если один из типов имеет внешнее ключевое свойство.  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`. Тип сущности `Book` имеет свойство `PublisherId`, которое ссылается на ключ сущности типа сущности `Publisher` при определении ограничения ссылочной целостности ассоциации `PublishedBy`.  
  
 ![рефконстраинтмодел](./media/foreign-key-property/reference-constraint-model.gif "Пример модели ссылочного ограничения")  
  
 [Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей. Следующий язык CSDL использует свойство внешнего ключа `PublisherId` для определения ограничения ссылочной целостности в ассоциации `PublishedBy`, приведенной ранее в концептуальной модели.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](entity-data-model-key-concepts.md)
- [Сущностная модель данных](entity-data-model.md)
