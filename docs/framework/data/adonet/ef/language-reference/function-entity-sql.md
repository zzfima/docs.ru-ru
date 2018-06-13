---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: c101032aed3e94e6bbf1d16319a616131fa6b60b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760678"
---
# <a name="function-entity-sql"></a>FUNCTION (Entity SQL)
Определяет функцию в рамках команды запроса Entity SQL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a>Аргументы  
 `function-name`  
 Имя функции.  
  
 `parameter-name`  
 Имя параметра функции.  
  
 `function_expression`  
 Допустимое выражение Entity SQL, представляющее функцию. Команда в функции может действовать, используя параметры `parameter_name` , переданные функции.  
  
 `data_type`  
 Имя поддерживаемого типа.  
  
 COLLECTION ( <type_definition`>` )  
 Выражение, возвращающее коллекцию поддерживаемых типов, строк или ссылок.  
  
 REF **(**`data_type`**)**  
 Выражение, возвращающее ссылку на тип сущности.  
  
 ROW **(**`row_expression`**)**  
 Выражение, возвращающее анонимные структурно типизированные записи из одного или нескольких значений. Дополнительные сведения см. в разделе [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="remarks"></a>Примечания  
 Объявить встроенными можно несколько функций с одинаковыми именами при условии, что эти функции имеют различные сигнатуры. Для получения дополнительной информации см. [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
 Встроенная функция может быть вызвана командой SQL только после определения ее в этой команде. Однако встроенная функция может быть вызвана в пределах другой встроенной функции как до, так и после определения вызываемой функции. В следующем примере функция A вызывает функцию B до того, как функция B была определена.  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Дополнительные сведения см. в разделе [как: вызов пользовательской функции](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02).  
  
 Функции также могут быть объявлены внутри самой модели. Функции, объявленные в модели, выполняются так же, как и функции, объявленные встроенными в команде. Дополнительные сведения см. в разделе [определяемые пользователем функции](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующей команде Entity SQL определяется функция `Products` , использующая целочисленное значение для фильтрации возвращаемых продуктов.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a>Пример  
 В следующей команде Entity SQL определяется функция `StringReturnsCollection` , использующая коллекцию строк для фильтрации возвращаемых контактов.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Язык Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
