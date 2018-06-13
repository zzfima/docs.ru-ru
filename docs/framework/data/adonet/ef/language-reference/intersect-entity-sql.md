---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 98515ccf111bf78f49347f744a1226ca1957fbb6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761536"
---
# <a name="intersect-entity-sql"></a>INTERSECT (Entity SQL)
Возвращает коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT. Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.  
  
## <a name="remarks"></a>Примечания  
 INTERSECT - один из операторов для работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов работы с наборами см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL использует оператор INTERSECT, чтобы вернуть коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
