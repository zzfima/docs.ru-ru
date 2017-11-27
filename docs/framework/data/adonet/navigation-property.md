---
title: "свойство навигации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1677ab1be071eeabd72b29c7ce61d01aaf6164a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="navigation-property"></a>свойство навигации
Объект *свойство навигации* — это необязательное свойство на [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) , позволяет переходить от одной [окончания](../../../../docs/framework/data/adonet/association-end.md) из [ассоциации](../../../../docs/framework/data/adonet/association-type.md) для другой конец. В отличие от других [свойства](../../../../docs/framework/data/adonet/property.md), свойства навигации не содержат данных.  
  
 Определение свойства навигации содержит следующую информацию.  
  
-   Имя. (Обязательный атрибут).  
  
-   Ассоциация, для которой осуществляется переход. (Обязательный атрибут).  
  
-   Конечные точки ассоциации, для которой осуществляется переход. (Обязательный атрибут).  
  
 Обратите внимание, что свойства навигации являются необязательными для обоих типов сущностей, расположенных в конечных элементах ассоциации. Если свойство навигации было определено для типа сущности на одном конечном элементе ассоциации, то определять его для типа сущности на другом конечном элементе необязательно.  
  
 Тип данных свойства навигации определяется [кратность](../../../../docs/framework/data/adonet/association-end-multiplicity.md) его удаленной [ассоциации](../../../../docs/framework/data/adonet/association-end.md). Например, предположим, что свойство навигации `OrdersNavProp` существует для типа сущности `Customer` и осуществляет навигацию по ассоциации «один ко многим» между `Customer` и `Order`. Поскольку конечная точка удаленной ассоциации для свойства навигации имеет кратность «много» (*), его тип данных - коллекция (элемент `Order`). Аналогично, если свойство навигации `CustomerNavProp` существует для типа сущности `Order`, то его тип данных будет `Customer`, поскольку кратность удаленного конечного элемента - «один» (1).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`. Свойства навигации, `Publisher` и `Authors`, определены относительно типа сущности «Book». Свойство навигации `Books` определено как относительно типа сущности «Publisher», так и относительно типа сущности `Author`.  
  
 ![Модель со свойствами навигации](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Обратите внимание, что атрибуты XML используются для сообщения сведений, необходимых для определения свойства навигации: атрибут `Name` содержит имя свойства, `Relationship` содержит имя ассоциации, для которой осуществляется переход, и `FromRole` и `ToRole` содержат конечные точки ассоциации.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели данных сущности](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)
