---
title: конечная точка набора ассоциаций
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 48ba84d46e380462405551cc2d826d84368b351a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786934"
---
# <a name="association-set-end"></a>конечная точка набора ассоциаций
*Конец набора ассоциаций* определяет [тип сущности](entity-type.md) и [набор сущностей](entity-set.md) в конце [набора ассоциаций](association-set.md). Конечные точки набора ассоциаций определяются как часть набора ассоциаций; набор ассоциаций должен иметь ровно две конечные точки.  
  
 Определение конечной точки набора ассоциаций содержит следующую информацию.  
  
- Один из типов сущностей, участвующих в наборе ассоциаций. (Обязательный атрибут).  
  
- Набор сущностей для типа сущностей, участвующих в наборе ассоциаций. (Обязательный атрибут).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.  
  
 ![Пример модели с тремя типами сущностей](./media/association-set-end/example-model-three-entity-types.gif)  
  
 На следующей схеме показаны один набор ассоциаций (`PublishedBy` и `Books`) и два набора сущностей (`Publishers`) на основе приведенной выше концептуальной модели. Конечные точки набора ассоциаций - это наборы сущностей `Books` и `Publishers`. Бизнес-аналитика в `Books` наборе сущностей представляет экземпляр `Book` типа сущности во время выполнения. Аналогичным образом PJ представляет `Publisher` экземпляр `Publishers` в наборе сущностей. Бипж представляет экземпляр `PublishedBy` ассоциации `PublishedBy` в наборе ассоциаций.  
  
 ![Снимок экрана, на котором показан пример набора.](./media/association-set-end/sets-example-association.gif)  
  
 В [Entity Framework ADO.NET](./ef/index.md) для определения концептуальных моделей используется DSL, именуемое языком определения концептуальной схемы ([CSDL](./ef/language-reference/csdl-specification.md)). Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме. Обратите внимание, что конечные точки набора ассоциаций определяются как часть каждого определения набора ассоциаций.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](entity-data-model-key-concepts.md)
- [Сущностная модель данных](entity-data-model.md)
