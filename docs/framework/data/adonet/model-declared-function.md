---
title: объявляемая моделью функция
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: c9abf9a3340cd22ab5d654588b1d22e10b5c05fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772116"
---
# <a name="model-declared-function"></a>объявляемая моделью функция
Объект *объявляемая моделью функция* является функцией, которая объявлена в концептуальной модели, но не определен в концептуальной модели. Функция может быть определена в среде размещения или хранения. Например, объявляемая моделью функция может быть сопоставлена функции, определенной в базе данных, экспонируя таким образом функцию в концептуальной модели на стороне сервера.  
  
 Объявление объявляемой моделью функции содержит следующую информацию.  
  
- Имя функции. (Обязательный атрибут).  
  
- Тип возвращаемого значения. (Необязательный параметр).  
  
    > [!NOTE]
    >  Если возвращаемое значение не задано, возвращаемого значения не будет.  
  
- Сведения о параметрах, включая имя и тип параметров. (Необязательный параметр).  
  
## <a name="example"></a>Пример  
 [ADO.NET Entity Framework](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) для определения концептуальных моделей. В языке CSDL, одна реализация объявляемой моделью функции является импорт функции (с помощью [элемент FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)). Далее на языке CSDL определяется контейнер сущностей с определением импорта функции. Обратите внимание, что возвращаемый тип для функции отсутствует, поскольку возвращаемый тип не задан.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
