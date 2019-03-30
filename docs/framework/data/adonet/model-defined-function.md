---
title: функция определенной модели
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 67821c68ee79b42bc54e22f1e15673d2d9243a68
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653864"
---
# <a name="model-defined-function"></a>функция определенной модели
Объект *определяемой моделью функции* — это функция, которая определена в концептуальной модели. Текст определяемой моделью функции выражается в [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), что позволяет функция может быть представлена независимо от правил или языков, поддерживаемых в источнике данных.  
  
 Определение определяемой моделью функции содержит следующие сведения.  
  
-   Имя функции. (Обязательный атрибут).  
  
-   Тип возвращаемого значения. (Необязательный параметр).  
  
    > [!NOTE]
    >  Если тип возвращаемого значения не задан, возвращаемого значения не будет.  
  
-   Сведения о параметрах. (Необязательный параметр).  
  
-   [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) выражение, которое определяет текст функции.  
  
 Обратите внимание, что определяемые моделью функции не поддерживают выходные параметры. Это ограничение введено, чтобы определяемые моделью функции можно было сочетать.  
  
## <a name="example"></a>Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Снимок экрана, показывающая модель с опубликованной датой.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. Следующий язык CSDL определяет функцию в концептуальной модели, которая возвращает числа лет с момента публикации экземпляра `Book` (ранее приведенного на схеме).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>См. также
- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
- [Модель EDM. Типы-примитивы](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
