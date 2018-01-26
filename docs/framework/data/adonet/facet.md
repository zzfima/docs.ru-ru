---
title: facet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 23346fe2095cea2b3f0d705c7d6d8914c35c06f7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="facet"></a>facet
Объект *аспекта* используется для добавления сведений в определение свойства примитивного типа. Объект [свойство](../../../../docs/framework/data/adonet/property.md) определение содержит сведения о типе свойства, но часто требуется больше сведений. Например, тип сущности в концептуальной модели может иметь свойство типа `String`, значение которого не может быть равно NULL. Аспекты позволяют задавать такой уровень сведений.  
  
 В следующей таблице описываются аспекты, поддерживаемые в модели EDM.  
  
> [!NOTE]
>  Точные значения и поведения аспектов определяются средой выполнения, использующей реализацию модели EDM.  
  
|Аспект|Описание|Применение|  
|-----------|-----------------|----------------|  
|`Collation`|Задает последовательность сортировки, которая будет использоваться при выполнении операций сравнения и упорядочивания для значений свойств.|`String`|  
|`ConcurrencyMode`|Указывает, что значение свойства должно использоваться в проверках оптимистического управления параллелизмом.|Все свойства примитивного типа|  
|`Default`|Задает значение по умолчанию для свойства в случае, если при создании экземпляра не было задано значение.|Все свойства примитивного типа|  
|`FixedLength`|Указывает, может ли изменяться длина значения свойства.|`Binary`, `String`|  
|`MaxLength`|Указывает максимальную длину значения свойства.|`Binary`, `String`|  
|`Nullable`|Задает, может ли свойство принимать значение NULL.|Все свойства примитивного типа|  
|`Precision`|Для свойств типа `Decimal` задается число цифр, которое может иметь значение свойства. Для свойств типа `Time`, `DateTime` и `DateTimeOffset` задается число цифр для части долей секунды значения свойства.|`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,|  
|`Scale`|Задает число цифр справа от десятичной запятой в значении свойства.|Десятичное число|  
|`Unicode`|Указывает, будет ли значение свойства храниться в Юникоде.|`String`|  
  
## <a name="example"></a>Пример  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее на языке CSDL определяется тип сущности `Book`. Обратите внимание, что аспекты реализуются как атрибуты XML. Значения аспекта указывают, что свойство не может быть задано со значением NULL и что свойства `Scale` и `Precision``Revision` имеют каждый значение 29.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
