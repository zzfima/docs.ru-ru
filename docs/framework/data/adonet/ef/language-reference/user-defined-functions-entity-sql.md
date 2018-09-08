---
title: Пользовательские функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 03146d895c6ca780692228937fafcf25b24902aa
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205371"
---
# <a name="user-defined-functions-entity-sql"></a>Пользовательские функции (Entity SQL)
Entity SQL поддерживает вызов встроенных определяемых пользователем функций в запросе. Вы можете определить эти встроенные функции с помощью запроса (см. в разделе [как: вызов пользовательской функции](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) или как часть концептуальной модели (см. в разделе [как: определения пользовательских функций в концептуальной модели](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)). Функции концептуальной модели определяются как команда Entity SQL в [DefiningExpression](https://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) элемент [функция](https://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) элемента в концептуальной модели.  
  
 Entity SQL позволяет определить функции в самой команде запроса. [ФУНКЦИЯ](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) оператор определяет встраиваемые функции. В одной команде можно задать несколько функций с одним и тем же именем при условии, что эти функции имеют уникальные сигнатуры. Для получения дополнительной информации см. [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
