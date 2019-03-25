---
title: тип ассоциации
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 895d7fdc464741723322717c3ace027dc49eed9c
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411451"
---
# <a name="association-type"></a>тип ассоциации
*Тип ассоциации* (также называемый ассоциацией) — это фундаментальный блок построения для описания связей в Entity Data Model (EDM). В концептуальной модели ассоциация представляет отношение между двумя [типы сущностей](../../../../docs/framework/data/adonet/entity-type.md) (такие как `Customer` и `Order`). В приложении экземпляр ассоциации представляет собой специфическую ассоциацию (такую как ассоциация между экземпляром `Customer` и экземпляром `Order`). Экземпляры ассоциации логически сгруппированы в [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md).  
  
 Определение ассоциации содержит следующую информацию.  
  
-   Уникальное имя. (Обязательный атрибут).  
  
-   Два [ассоциации](../../../../docs/framework/data/adonet/association-end.md), один для каждого типа сущности в отношении. (Обязательный атрибут).  
  
    > [!NOTE]
    >  Ассоциация не может представлять связь между более чем двумя типами сущностей. Ассоциация может, тем не менее, определять связь с самим собой посредством указания одного и того же типа сущности для каждой из его конечных точек ассоциаций.  
  
-   Объект [ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Необязательный параметр).  
  
 Каждая конечная точка ассоциации необходимо указать [кратность конечной](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , указывающее число экземпляров типа сущности, которые могут быть на одном конце ассоциации. Кратность конечной точки ассоциации может иметь значение (1), ноль или один (0.. 1) или многие (\*). Экземпляры типа сущности на одном конце ассоциации может осуществляться через [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) или внешних ключей, если они экспонируются типом сущности. Дополнительные сведения см. в разделе [модели EDM: Внешние ключи](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`. Кратность `Publisher` один (1), а кратность `Book` окончания многих (\*), том, что издатель публикует много книг, и одна книга публикуется одним издателем.  
  
 ![Пример модели с тремя типами сущностей](./media/association-type/example-model-three-entity-types.gif)  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
