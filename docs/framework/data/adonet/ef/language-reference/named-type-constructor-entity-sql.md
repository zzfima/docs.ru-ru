---
title: Конструктор именованных типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: 9ffaf55ed54e8479a56e6f9fc4d7a5efe47f8e2a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="named-type-constructor-entity-sql"></a>Конструктор именованных типов (Entity SQL)
Используется для создания экземпляров номинальных типов концептуальной модели, например сложных типов или типов сущностей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Аргументы  
 `identifier`  
 Значение, представляющее собой простой или заключенный в кавычки идентификатор. Дополнительные сведения см. в разделе [идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 `expression`  
 Атрибуты типа, которые, как предполагается, должны располагаться в таком же порядке, как и в декларации этого типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Экземпляры именованных сложных типов и типов сущностей.  
  
## <a name="remarks"></a>Примечания  
 В следующих примерах показано, как создавать номинальные и сложные типы.  
  
 Приведенное далее выражение создает экземпляр типа `Person` .  
  
 `Person("abc", 12)`  
  
 Приведенное далее выражение создает экземпляр сложного типа.  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 Приведенное далее выражение создает экземпляр вложенного сложного типа.  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 Приведенное далее выражение создает экземпляр сущности с вложенным сложным типом.  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 В следующем примере показано, как инициализировать свойство сложного типа значением null:`MyModel.ZipCode(‘98118’, null)`.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL конструктор именованного типа используется для создания экземпляра типа концептуальной модели. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a>См. также  
 [Сборка типов](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
