---
title: "тип сущности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1b84ff5a55cff4548539e81b16406e234dcb43f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="entity-type"></a>тип сущности
*Тип сущности* это фундаментальный блок построения для описания структуры данных с помощью модели данных сущности (EDM). В концептуальной модели тип сущности представляет структуру основных концептуальных элементов верхнего уровня, таких как клиенты или заказы. Тип сущности - это шаблон для экземпляров типов сущностей. Каждый шаблон содержит следующие сведения.  
  
-   Уникальное имя. (Обязательно).  
  
-   [Ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) определяется одно или несколько свойств. (Обязательно).  
  
-   Данные в виде [свойства](../../../../docs/framework/data/adonet/property.md). (Необязательно.)  
  
-   [Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) , которые позволяют переходить от одного [окончания](../../../../docs/framework/data/adonet/association-end.md) из [ассоциации](../../../../docs/framework/data/adonet/association-type.md) к другой стороне. (Необязательный параметр).  
  
 В приложении экземпляр типа сущности представляет определенный объект (например, определенного клиента или заказ). Каждый экземпляр типа сущности должен иметь уникальный [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) в [набора сущностей](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Два экземпляра типа сущности считаются равными, только если они являются экземплярами одного типа и значения их ключей сущности равны.  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Обратите внимание, что свойства каждого типа сущности, составляющего его ключ сущности, обозначаются знаком «(Ключ)».  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели данных сущности](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [facet](../../../../docs/framework/data/adonet/facet.md)
