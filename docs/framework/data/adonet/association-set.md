---
title: "набор ассоциаций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db293cbc636d0ae4e532f24b2852444395f603c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="association-set"></a>набор ассоциаций
*Набора ассоциаций* — это логический контейнер для [ассоциации](../../../../docs/framework/data/adonet/association-type.md) экземпляров того же типа. Набор ассоциаций не является конструктом моделирования данных, то есть не описывает структуру данных или связи. Вместо этого ассоциация обеспечивает конструкт для среды размещения или хранения (например, для среды CLR или базы данных сервера SQL), позволяя группировать экземпляры ассоциаций так, чтобы они были сопоставлены хранилищу данных.  
  
 Набор ассоциаций определяется внутри [контейнер сущностей](../../../../docs/framework/data/adonet/entity-container.md), который является логической группой [наборов сущностей](../../../../docs/framework/data/adonet/entity-set.md) и наборы ассоциаций.  
  
 Определение набора ассоциаций содержит следующую информацию.  
  
-   Имя набора ассоциаций. (Обязательный атрибут).  
  
-   Ассоциация, экземпляры которой будут являться содержимым. (Обязательный атрибут).  
  
-   Два [конечные точки набора ассоциаций](../../../../docs/framework/data/adonet/association-set-end.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`. Информации о наборах ассоциаций не содержится в схеме, однако на следующей схеме показан пример наборов ассоциаций и наборов сущностей на основе этой модели.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 В следующем примере показан набор ассоциаций (`PublishedBy`) и два набора сущностей (`Books` и `Publishers`) на основе приведенной выше концептуальной модели. Бизнес-аналитики в `Books` набор сущностей представляет экземпляр `Book` тип сущности во время выполнения. Аналогичным образом представляет Pj `Publisher` экземпляра в `Publishers` набора сущностей. BiPj представляет экземпляр `PublishedBy` ассоциации в `PublishedBy` набора ассоциаций.  
  
 ![Задает пример](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме. Обратите внимание, что имя и ассоциация для каждого набора ассоциаций определены при помощи атрибутов XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Можно определить несколько наборов ассоциаций на одну ассоциацию, при условии, что нет общей папки связи двух наборов [конечная точка набора ассоциаций](../../../../docs/framework/data/adonet/association-set-end.md). Далее на языке CSDL определяется контейнер сущностей с двумя наборами ассоциаций для ассоциации `WrittenBy`: Обратите внимание, что несколько наборов сущностей были определены для типов сущностей `Book` и `Author` и что наборы ассоциаций не имеют одной и той же конечной точки ассоциации.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели данных сущности](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [Свойство внешнего ключа](../../../../docs/framework/data/adonet/foreign-key-property.md)
