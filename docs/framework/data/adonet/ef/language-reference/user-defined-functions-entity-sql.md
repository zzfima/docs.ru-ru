---
title: Пользовательские функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 86b7d26e7959be954b4ddd7404f3a3ad6c76c1c5
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904509"
---
# <a name="user-defined-functions-entity-sql"></a>Пользовательские функции (Entity SQL)
Entity SQL поддерживает вызов встроенных определяемых пользователем функций в запросе. Вы можете определить эти встроенные функции с помощью запроса (см. в разделе [как: Вызов пользовательской функции](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) или как часть концептуальной модели (см. в разделе [как: Определения пользовательских функций в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))). Функции концептуальной модели определяются как команда Entity SQL в [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) элемент [функция](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) элемента в концептуальной модели.  
  
 Entity SQL позволяет определить функции в самой команде запроса. [ФУНКЦИЯ](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) оператор определяет встраиваемые функции. В одной команде можно задать несколько функций с одним и тем же именем при условии, что эти функции имеют уникальные сигнатуры. Для получения дополнительной информации см. [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>См. также
- [Функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
