---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: b3ebd4a7fe9d9e1324210d9f4d1265115bd8617f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cast-entity-sql"></a>CAST (Entity SQL)
Преобразует выражение одного типа данных в другой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение, которое можно преобразовать в `data_type`.  
  
 `data_type`  
 Целевой тип данных, предоставляемый системой. Это должен быть (скалярный) тип-примитив. Какой тип `data_type` будет использован, зависит от области запроса. Если запрос выполняется с командой <xref:System.Data.EntityClient.EntityCommand>, то типом данных будет тип, определенный в концептуальной модели. Для получения дополнительной информации см. [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md). Если запрос выполняется командой <xref:System.Data.Objects.ObjectQuery%601>, то этим типом данных будет тип CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение такого же типа, что и аргумент `data_type`.  
  
## <a name="remarks"></a>Примечания  
 Семантика выражения явного приведения такая же, как у выражения [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT. Выражение явного приведения используется для преобразования значения одного типа в значение другого типа.  
  
```  
CAST( e as T )  
```  
  
 Если «e» имеет некий тип S, а S можно преобразовать в T, то приведенное выше выражение является допустимым выражением явного приведения. Т должно иметь (скалярный) тип-примитив.  
  
 При явном приведении к `Edm.Decimal`можно дополнительно указать значения аспектов точности и масштаба. Если они не заданы явным образом, принимаются значения по умолчанию для точности и масштаба 18 и 0 соответственно. В частности, для `Decimal`поддерживаются следующие перегрузки:  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 Использование выражения явного приведения считается явным преобразованием. При явном преобразовании возможно усечение данных и потеря точности.  
  
> [!NOTE]
>  Операция CAST может выполняться только над типами-примитивами и типами элементов перечисления.  
  
## <a name="example"></a>Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор CAST используется для явного приведения выражения одного типа данных к другому. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
