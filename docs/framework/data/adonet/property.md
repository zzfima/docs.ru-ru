---
title: свойство;
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: bc8f890479e195f1e6ef847219a74f165c722fd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589429"
---
# <a name="property"></a>свойство;
*Свойства* являются базовыми стандартными блоками [типы сущностей](../../../../docs/framework/data/adonet/entity-type.md) и [сложные типы](../../../../docs/framework/data/adonet/complex-type.md). Свойства определяют форму и характеристики данных, которые экземпляр типа сущности или сложного типа будет содержать. Свойства в концептуальной модели аналогичны свойствам, которые определены применительно к классу. По такому же принципу, как свойства, относящиеся к классу, определяют форму класса и несут информацию об объектах, свойства в концептуальной модели определяют форму типа сущности и несут информацию об экземплярах типа сущности.  
  
> [!NOTE]
>  Свойства, как они описаны в этом разделе, отличаются от свойств навигации. Дополнительные сведения см. в разделе [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md).  
  
 Определение свойства содержит следующую информацию.  
  
-   Имя свойства. (Обязательный атрибут).  
  
-   Тип свойства. (Обязательный атрибут).  
  
-   Набор [аспекты](../../../../docs/framework/data/adonet/facet.md). (Необязательный параметр).  
  
 Свойство может содержать примитивные данные (такие как строка, целое число, логическое значение) или структурированные данные (такие как сложный тип). Свойства примитивного типа также называются скалярными свойствами. Дополнительные сведения см. в разделе [модели EDM: Типы-примитивы](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).  
  
> [!NOTE]
>  Сложный тип может сам по себе иметь свойства, которые являются сложными типами.  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`. Каждый тип сущности имеет несколько свойств, однако сведений о типе для каждого свойства в схеме не содержится. Свойства, которые являются [ключи сущностей](../../../../docs/framework/data/adonet/entity-key.md) , обозначаются знаком (ключ).  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее на языке CSDL определяется тип сущности `Book` (как показано на схеме выше), и при помощи атрибутов XML указываются тип и имя каждого свойства. Дополнительный аспект, `Nullable`, также определяется при помощи атрибута XML.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Ни одно из свойств на схеме не может быть свойством сложного типа. Например, свойство `Address` в типе сущности `Publisher` может быть свойством сложного типа, состоящего из нескольких скалярных свойств, таких как `StreetAddress`, `City`, `StateOrProvince`, `Country` и `PostalCode`. Представление такого сложного типа на языке CSDL может быть следующим.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>См. также
- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
