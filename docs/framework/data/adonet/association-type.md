---
title: "тип ассоциации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5349889017ea23701a17a92947d9750610a52f59
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="association-type"></a>тип ассоциации
*Тип ассоциации* (также называемый ассоциацией) это фундаментальный блок построения для описания связей в модели данных сущности (EDM). В концептуальной модели ассоциация представляет собой связь между двумя [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md) (такие как `Customer` и `Order`). В приложении экземпляр ассоциации представляет собой специфическую ассоциацию (такую как ассоциация между экземпляром `Customer` и экземпляром `Order`). Экземпляры ассоциации логически сгруппированы в [набора ассоциаций](../../../../docs/framework/data/adonet/association-set.md).  
  
 Определение ассоциации содержит следующую информацию.  
  
-   Уникальное имя. (Обязательный атрибут).  
  
-   Два [ассоциации](../../../../docs/framework/data/adonet/association-end.md), один для каждого типа сущности в связи. (Обязательный атрибут).  
  
    > [!NOTE]
    >  Ассоциация не может представлять связь между более чем двумя типами сущностей. Ассоциация может, тем не менее, определять связь с самим собой посредством указания одного и того же типа сущности для каждой из его конечных точек ассоциаций.  
  
-   Объект [ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Необязательный параметр).  
  
 Каждая конечная точка ассоциации необходимо указать [кратность конечной точки ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , указывающее количество экземпляров типа сущности, которые могут быть на одном конце связи. Кратность конечной точки ассоциации может иметь значение «один» (1), «нуль или один» (0..1) или «много» (*). Экземпляры типа сущности на одном конце связи может осуществляться через [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) или внешних ключей, если они предоставляются в типе сущности. Дополнительные сведения см. в разделе [модель EDM: внешние ключи](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`. Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*), что означает, что издатель публикует много книг, а одна книга публикуется одним издателем.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
