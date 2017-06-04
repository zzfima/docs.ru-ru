---
title: "сложный тип | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# сложный тип
*Сложный тип* \- это шаблон для определения сложных, структурированных свойств в [типах сущностей](../../../../docs/framework/data/adonet/entity-type.md) или в других сложных типах.  Каждый шаблон содержит следующие сведения.  
  
-   Уникальное имя.  \(Обязательный атрибут\).  
  
    > [!NOTE]
    >  Имя сложного типа не может быть таким же, что и имя типа сущности внутри одного и того же пространства имени.  
  
-   Данные в форме одного и нескольких [свойств](../../../../docs/framework/data/adonet/property.md).  \(Необязательно.\)  
  
    > [!NOTE]
    >  Свойство сложного типа может быть другим сложным типом.  
  
 Сложный тип похож на тип сущности тем, что сложный тип может содержать полезные данные в форме свойств примитивного типа или других сложных типов.  Однако между сложными типами и типами сущности существуют некоторые ключевые различия.  
  
-   Сложные типы не имеют идентификаторов и поэтому не могут существовать независимо.  Сложные типы могут существовать только как свойства типов сущностей или других сложных типов.  
  
-   Сложные типы не могут участвовать в [сопоставлениях](../../../../docs/framework/data/adonet/association-type.md).  Ни один конец ассоциации не может быть сложным типом, и поэтому [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) не могут быть определены для сложных типов.  
  
## Пример  
 Платформа [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Далее на языке CSDL определяется сложный тип, адрес со свойствами примитивного типа `StreetAddress`, `City`, `StateOrProvince`, `Country` и `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Чтобы определить сложный тип `Address` \(показанный выше\) как свойство типа сущности, необходимо объявить тип свойства в определении типа сущности.  Далее на языке CSDL объявляется свойство `Address` в виде сложного типа в типе сущности \(издателе\).  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)