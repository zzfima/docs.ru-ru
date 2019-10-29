---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 7c1e02d44c674bf262f92df1c43bec6e9f2143c5
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039926"
---
# <a name="case-entity-sql"></a>CASE (Entity SQL)
Вычисляет набор выражений типа `Boolean` для определения результата.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a>Аргументы  
 `n`  
 Заполнитель, который показывает, что можно использовать несколько предложений WHEN `Boolean_expression` THEN `result_expression` .  
  
 THEN `result_expression`  
 Выражение, возвращаемое, если результатом выражения `Boolean_expression` является значение `true`. `result expression` - любое допустимое выражение.  
  
 ELSE `else_result_expression`  
 Это выражение, возвращаемое, если ни одна из операций сравнения не дает в результате `true`. Если этот аргумент опущен и ни одна из операций сравнения не дает в результате `true`, функция CASE возвращает NULL. `else_result_expression` - любое допустимое выражение. Типы данных аргумента `else_result_expression` и любого из аргументов `result_expression` должны быть одинаковыми или неявно приводимыми друг к другу.  
  
 WHEN `Boolean_expression`  
 Выражение типа `Boolean` , вычисляемое при использовании поискового формата оператора CASE. `Boolean_expression` - любое допустимое выражение типа `Boolean` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип с наивысшим приоритетом из набора типов в выражении `result_expression` и необязательном выражении `else_result_expression`.  
  
## <a name="remarks"></a>Заметки  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выражение CASE напоминает выражение CASE языка Transact-SQL. Выражение CASE применяется для выполнения ряда проверок условий в целях определения того, вычисление какого выражения приведет к получению приемлемого результата. В этой форме выражение CASE применяется к ряду, состоящему из одного или нескольких выражений типа `Boolean` , для определения правильного результирующего выражения.  
  
 Функция CASE находит значение `Boolean_expression` для каждого предложения WHEN в указанном порядке и возвращает значение `result_expression` первого выражения `Boolean_expression` , которое определяется как `true`. Остальные выражения оцениваться не будут. Если ни одно выражение `Boolean_expression` не вычисляется в `true`, компонент Database Engine возвращает выражение `else_result_expression` , если указано предложение ELSE, или значение NULL, если предложение ELSE не указано.  
  
 Инструкция CASE не может возвращать мультинабор.  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL с помощью выражения CASE оценивает набор выражений типа `Boolean` , чтобы определить результат. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>См. также

- [THEN](then-entity-sql.md)
- [SELECT](select-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
