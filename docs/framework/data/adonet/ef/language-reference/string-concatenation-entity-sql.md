---
title: + (Объединение строк) (Язык entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: e53bd0a2607deb67d45edc44e51cf4ad283b21c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54633937"
---
# <a name="-string-concatenation-entity-sql"></a>+ (объединение строк) (Entity SQL)
Объединяет две строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение с типом данных EDM.String. Оба выражения должны быть одного типа данных, либо должна иметься возможность неявного преобразования типа данных одного выражения в тип данных другого выражения.  
  
## <a name="result-types"></a>Типы результата  
 Тип данных, который является результатом неявного повышения типов обоих аргументов. Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL с помощью оператора «+» объединяются две строки. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a>См. также
- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Типы концептуальной модели (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
