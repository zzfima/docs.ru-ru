---
title: тип ассоциации
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 17465dbec3f5e2896cf755a1f8585734388f54ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948301"
---
# <a name="association-type"></a>тип ассоциации
*Тип ассоциации* (называемый также Ассоциацией) — это фундаментальный Стандартный блок для описания связей в EDM (EDM). В концептуальной модели Ассоциация представляет связь между двумя [типами сущностей](../../../../docs/framework/data/adonet/entity-type.md) (например `Customer` , и `Order`). В приложении экземпляр ассоциации представляет собой специфическую ассоциацию (такую как ассоциация между экземпляром `Customer` и экземпляром `Order`). Экземпляры ассоциаций логически группируются в [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md).  
  
 Определение ассоциации содержит следующую информацию.  
  
- Уникальное имя. (Обязательный атрибут).  
  
- Две [ассоциации завершаются](../../../../docs/framework/data/adonet/association-end.md), по одной для каждого типа сущности в связи. (Обязательный атрибут).  
  
    > [!NOTE]
    > Ассоциация не может представлять связь между более чем двумя типами сущностей. Ассоциация может, тем не менее, определять связь с самим собой посредством указания одного и того же типа сущности для каждой из его конечных точек ассоциаций.  
  
- [Ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Необязательный параметр).  
  
 Каждый элемент ассоциации должен указывать количество [элементов ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , которое указывает число экземпляров типа сущности, которые могут находиться на одном конце ассоциации. Кратность окончания ассоциации может иметь значение один (1), ноль или один (0.. 1) или многие (\*). Доступ к экземплярам типа сущности на одном конце ассоциации возможен через [Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) или внешние ключи, если они представлены в типе сущности. Дополнительные сведения см. в [разделе EDM: Внешние ключи](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`. Кратность `Publisher` конца равна единице (1), а кратность `Book` End — many (\*), что означает, что издатель публикует много книг, а книга публикуется одним издателем.  
  
 ![Пример модели с тремя типами сущностей](./media/association-type/example-model-three-entity-types.gif)  
  
 [Entity Framework ADO.NET](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), для определения концептуальных моделей. Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
