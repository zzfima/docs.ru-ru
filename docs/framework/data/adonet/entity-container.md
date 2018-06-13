---
title: контейнер сущностей
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: ed2123629c61b179e07e86effa0c39d9a3222b62
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764045"
---
# <a name="entity-container"></a>контейнер сущностей
*Контейнер сущностей* представляет собой логическое группирование [наборов сущностей](../../../../docs/framework/data/adonet/entity-set.md), [наборов ассоциаций](../../../../docs/framework/data/adonet/association-set.md), и [функции imports](../../../../docs/framework/data/adonet/model-declared-function.md).  
  
 Для контейнера сущностей, определенного в концептуальной модели, должны выполняться следующие условия.  
  
-   В каждой концептуальной модели должен быть определен по крайней мере один контейнер сущностей.  
  
-   Контейнер сущностей должен иметь уникальное имя внутри концептуальной модели.  
  
 Контейнер сущностей может определять наборы сущностей или наборы ассоциаций, которые используют типы сущностей или ассоциации, определенные в одном или нескольких пространствах имен. Дополнительные сведения см. в разделе [модель EDM: пространства имен](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  Дополнительные сведения см. в следующем примере.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Схема не содержит сведений о контейнере сущностей, тем не менее, концептуальная модель должна определять контейнер сущностей. [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Далее на языке CSDL определяется контейнер сущностей для концептуальной модели, приведенной на схеме выше. Обратите внимание, что имя контейнера сущностей определяется в атрибуте XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
