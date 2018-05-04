---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: df194a26b36ba50d7b55c3dda6053c883ba9b228
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Создает экземпляр мультинабора из списка значений. Все значения конструктора MULTISET должны принадлежать совместимому типу `T`. Применение пустых конструкторов мультинаборов не допускается.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любой допустимый список значений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Коллекция типа MULTISET\<T >.  
  
## <a name="remarks"></a>Примечания  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет три типа конструкторов: конструкторы строк, конструкторы объектов и конструкторы мультинаборов (или коллекций). Дополнительные сведения см. в разделе [типов, создав](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 Конструктор мультинаборов создает экземпляр мультинабора из списка значений. Все значения конструктора MULTISET должны принадлежать совместимому типу.  
  
 Например, следующее выражение создает мультинабор целых чисел.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  Вложенные литералы мультинаборов поддерживаются лишь в тех случаях, когда мультинабор-упаковщик имеет лишь один элемент мультинабора, например `{{1, 2, 3}}`. Когда же мультинабор-упаковщик имеет несколько элементов мультинабора (например, `{{1, 2}, {3, 4}}`), вложенные литералы мультинаборов не поддерживаются.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор MULTISET используется для создания экземпляра мультинабора из списка значений. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>См. также  
 [Сборка типов](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
