---
title: функция определенной модели
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 05a44e86a118b649490cde849c8ca2c2bb0d2f15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934519"
---
# <a name="model-defined-function"></a>функция определенной модели
*Определяемая моделью функция* — это функция, определенная в концептуальной модели. Текст функции, определяемой моделью, выражается в [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), что позволяет выражать функцию независимо от правил или языков, поддерживаемых в источнике данных.  
  
 Определение определяемой моделью функции содержит следующие сведения.  
  
- Имя функции. (Обязательный атрибут).  
  
- Тип возвращаемого значения. (Необязательный параметр).  
  
    > [!NOTE]
    > Если тип возвращаемого значения не задан, возвращаемого значения не будет.  
  
- Сведения о параметрах. (Необязательный параметр).  
  
- Выражение [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) , определяющее текст функции.  
  
 Обратите внимание, что определяемые моделью функции не поддерживают выходные параметры. Это ограничение введено, чтобы определяемые моделью функции можно было сочетать.  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Снимок экрана, на котором показана модель с опубликованной датой.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 [Entity Framework ADO.NET](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), для определения концептуальных моделей. Следующий язык CSDL определяет функцию в концептуальной модели, которая возвращает числа лет с момента публикации экземпляра `Book` (ранее приведенного на схеме).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
- [EDM: Примитивные типы данных](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
