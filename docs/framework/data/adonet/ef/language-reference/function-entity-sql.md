---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: ae8da3985f11a2e9f52852876a21f50a412e3b27
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250935"
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
  
 Коллекция (< type_definition`>` )  
 Выражение, возвращающее коллекцию поддерживаемых типов, строк или ссылок.  
  
 REF **(** `data_type` **)**  
 Выражение, возвращающее ссылку на тип сущности.  
  
 ROW **(** `row_expression` **)**  
 Выражение, возвращающее анонимные структурно типизированные записи из одного или нескольких значений. Дополнительные сведения см. в разделе [ROW](row-entity-sql.md).  
  
## <a name="remarks"></a>Примечания  
 Объявить встроенными можно несколько функций с одинаковыми именами при условии, что эти функции имеют различные сигнатуры. Для получения дополнительной информации см. [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
 Встроенная функция может быть вызвана командой SQL только после определения ее в этой команде. Однако встроенная функция может быть вызвана в пределах другой встроенной функции как до, так и после определения вызываемой функции. В следующем примере функция A вызывает функцию B до того, как функция B была определена.  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Вызов определяемой пользователем функции](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).  
  
 Функции также могут быть объявлены внутри самой модели. Функции, объявленные в модели, выполняются так же, как и функции, объявленные встроенными в команде. Дополнительные сведения см. в разделе [определяемые пользователем функции](user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующей команде Entity SQL определяется функция `Products` , использующая целочисленное значение для фильтрации возвращаемых продуктов.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a>Пример  
 В следующей команде Entity SQL определяется функция `StringReturnsCollection` , использующая коллекцию строк для фильтрации возвращаемых контактов.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Язык Entity SQL](entity-sql-language.md)
