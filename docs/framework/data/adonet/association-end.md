---
title: "конечная точка ассоциации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ffa768f50b3a80c22b4c84cffaf42897193a7d9f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="association-end"></a>конечная точка ассоциации
*Ассоциации* идентифицирует [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) на одном конце [ассоциации](../../../../docs/framework/data/adonet/association-type.md) и число сущностей введите экземпляров, которые могут существовать в конечной точке ассоциации. Элементы ассоциации определяются при определении ассоциации; ассоциация должна иметь два элемента. [Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) позволяют осуществлять переход от одного конечного элемента ассоциации к другому.  
  
 Определение конечной точки ассоциации содержит следующую информацию.  
  
-   Один из типов сущности, участвующий в ассоциации. (Обязательный атрибут).  
  
    > [!NOTE]
    >  Для одной ассоциации тип сущности, указанный для каждой конечной точки ассоциации, может быть одним и тем же. Так создается самоассоциация.  
  
-   [Кратность конечной точки ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , указывающее количество экземпляров типа сущности, которые могут быть на одном конце связи. Кратность конечной точки ассоциации может иметь значение «один» (1), «нуль или один» (0..1) или «много» (*).  
  
-   Имя для элемента ассоциации. (Необязательный параметр).  
  
-   Сведения об операциях, которые выполняются на конечной точке ассоциации, например каскадная операция удаления. (Необязательный параметр).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`. Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*), что означает, что издатель публикует много книг, а одна книга публикуется одним издателем.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Платформа ADO.NET Entity Framework использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Ниже язык определения концептуальной схемы определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме. Обратите внимание, что тип, имя и кратность каждой конечной точки ассоциации указаны атрибутами XML (атрибуты `Type`, `Role` и `Multiplicity` соответственно). Дополнительные сведения об операциях, выполненных на конечной точке, указываются в элементе XML (элемент `OnDelete`). В данном случае, если издатель удаляется, удаляются и все связанные книги.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
