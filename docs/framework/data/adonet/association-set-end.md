---
title: конечная точка набора ассоциаций
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769594"
---
# <a name="association-set-end"></a>конечная точка набора ассоциаций
*Конечная точка набора ассоциаций* идентифицирует [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и [набор сущностей](../../../../docs/framework/data/adonet/entity-set.md) в конце [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md). Конечные точки набора ассоциаций определяются как часть набора ассоциаций; набор ассоциаций должен иметь ровно две конечные точки.  
  
 Определение конечной точки набора ассоциаций содержит следующую информацию.  
  
- Один из типов сущностей, участвующих в наборе ассоциаций. (Обязательный атрибут).  
  
- Набор сущностей для типа сущностей, участвующих в наборе ассоциаций. (Обязательный атрибут).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.  
  
 ![Пример модели с тремя типами сущностей](./media/association-set-end/example-model-three-entity-types.gif)  
  
 На следующей схеме показаны один набор ассоциаций (`PublishedBy` и `Books`) и два набора сущностей (`Publishers`) на основе приведенной выше концептуальной модели. Конечные точки набора ассоциаций - это наборы сущностей `Books` и `Publishers`. Бизнес-аналитики в `Books` набор сущностей представляет экземпляр `Book` тип сущности во время выполнения. Аналогичным образом, представляет Pj `Publisher` в экземпляре `Publishers` набора сущностей. BiPj представляет экземпляр `PublishedBy` ассоциации в `PublishedBy` набора ассоциаций.  
  
 ![Снимок экрана, показывающий пример наборов.](./media/association-set-end/sets-example-association.gif)  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует DSL, называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме. Обратите внимание, что конечные точки набора ассоциаций определяются как часть каждого определения набора ассоциаций.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
