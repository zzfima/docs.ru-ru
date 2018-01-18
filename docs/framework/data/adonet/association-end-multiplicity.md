---
title: "кратность конечной точки ассоциации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 36f6d22a8fd3a3c0f1fd997d5101b9fdf8e91a8c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="association-end-multiplicity"></a>кратность конечной точки ассоциации
*Кратность конечной точки ассоциации* определяет количество [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) экземпляров, которые могут быть на одном конце [ассоциации](../../../../docs/framework/data/adonet/association-type.md).  
  
 Кратность конечной точки ассоциации может иметь одно из следующих значений.  
  
-   «один» (1): показывает, что на конечной точке ассоциации существует ровно один экземпляр типа сущности.  
  
-   «ноль или один» (0..1): показывает, что на конечной точке ассоциации существует ноль, один или несколько экземпляров типа сущности.  
  
-   «много» (*): показывает, что на конечной точке ассоциации существует ноль, один или несколько экземпляров типа сущности.  
  
 Ассоциация зачастую характеризуется кратностями конечной точки ассоциации. Например, если конечные точки ассоциации имеют кратности «один» (1) и «много» (*), ассоциация называется ассоциацией «один-ко-многим». В следующем примере ассоциация `PublishedBy` является ассоциацией «один-ко-многим» (один издатель публикует много книг, а одна книга публикуется одним издателем). Ассоциация `WrittenBy` является ассоциацией «один-ко-многим» (одна книга может иметь несколько авторов, а один автор может написать несколько книг).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`. Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*).  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Платформа ADO.NET Entity Framework использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
