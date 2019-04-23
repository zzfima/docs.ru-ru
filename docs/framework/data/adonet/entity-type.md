---
title: тип сущности
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 026b0aef7cf2de8fe222721191afa459859701ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108268"
---
# <a name="entity-type"></a>тип сущности
*Тип сущности* — это фундаментальный блок построения для описания структуры данных Entity Data Model (EDM). В концептуальной модели тип сущности представляет структуру основных концептуальных элементов верхнего уровня, таких как клиенты или заказы. Тип сущности - это шаблон для экземпляров типов сущностей. Каждый шаблон содержит следующие сведения.  
  
-   Уникальное имя. (Обязательно).  
  
-   [Ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) определяется одно или несколько свойств. (Обязательно).  
  
-   Данные в виде [свойства](../../../../docs/framework/data/adonet/property.md). (Необязательно.)  
  
-   [Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) , которые позволяют переходить от одного [окончания](../../../../docs/framework/data/adonet/association-end.md) из [ассоциации](../../../../docs/framework/data/adonet/association-type.md) к другой стороне. (Необязательный параметр).  
  
 В приложении экземпляр типа сущности представляет определенный объект (например, определенного клиента или заказ). Каждый экземпляр типа сущности должен иметь уникальный [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) в [набор сущностей](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Два экземпляра типа сущности считаются равными, только если они являются экземплярами одного типа и значения их ключей сущности равны.  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Пример модели с тремя типами сущностей](./media/entity-type/example-model-three-entity-types.gif)  
  
 Обратите внимание, что свойства каждого типа сущности, составляющего его ключ сущности, обозначаются знаком «(Ключ)».  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facet](../../../../docs/framework/data/adonet/facet.md)
