---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 097d6e7d452ee62a2c8934d2c5fcfdddbeaffc73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772376"
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Определяет, относится ли тип выражения к указанному типу или одному из его подтипов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса для определения типа.  
  
 NOT  
 Выполняет отрицание результата EDM.Boolean для IS OF.  
  
 ONLY  
 Указывает, что оператор IS OF возвращает значение `true` только в том случае, если выражение `expression` относится к типу `type`, а не одному из его подтипов.  
  
 `type`  
 Тип, по которому проверяется выражение `expression`. Для типа должно быть указано пространство имен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если выражение `expression` относится к типу T, который является либо базовым типом, либо производным типом от типа `type`. Значение null, если выражение `expression` во время выполнения имеет значение null. В противном случае - значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Выражения `expression IS NOT OF (type)` и `expression IS NOT OF (ONLY type)` являются синтаксическими эквивалентами `NOT (expression IS OF (type))` и `NOT (expression IS OF (ONLY type))`, соответственно.  
  
 В следующей таблице показано, каким образом оператор `IS OF` работает с некоторыми стандартными и нестандартными конструкциями. Все исключения формируются на стороне клиента перед вызовом поставщика.  
  
|Шаблон|Поведение|  
|-------------|--------------|  
|null IS OF (EntityType)|Активизирует исключение|  
|null IS OF (ComplexType)|Активизирует исключение|  
|null IS OF (RowType)|Активизирует исключение|  
|TREAT (null AS EntityType) IS OF (EntityType)|Возвращает DBNull|  
|TREAT (null AS ComplexType) IS OF (ComplexType)|Активизирует исключение|  
|TREAT (null AS RowType) IS OF (RowType)|Активизирует исключение|  
|EntityType IS OF (EntityType)|Возвращает значение true или false|  
|ComplexType IS OF (ComplexType)|Активизирует исключение|  
|RowType IS OF (RowType)|Активизирует исключение|  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запроса оператор IS OF используется для определения типа выражения запроса, а затем оператор TREAT используется для преобразования объекта типа Course в коллекцию объектов типа OnsiteCourse. Запрос основан на [модели School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
